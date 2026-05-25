---
name: pufferlib
description: 针对速度和规模优化的 high-performance reinforcement learning framework。当需要 fast parallel training、vectorized environments、multi-agent systems，或与 game environments（Atari、Procgen、NetHack）集成时使用。相比标准实现可实现 2-10x speedups。如需快速 prototyping 或文档丰富的标准 algorithm implementations，请改用 stable-baselines3。
license: MIT license
metadata:
    skill-author: K-Dense Inc.
---

# PufferLib - High-Performance Reinforcement Learning

## 概览

PufferLib 是一个 high-performance reinforcement learning library，面向快速 parallel environment simulation 和 training 设计。它通过 optimized vectorization、native multi-agent support 和高效 PPO implementation（PuffeRL）实现每秒数百万 steps 的 training。该 library 提供包含 20+ environments 的 Ocean suite，并与 Gymnasium、PettingZoo 和 specialized RL frameworks 无缝集成。

## 何时使用此 Skill

在以下场景使用此 skill：
- **Training RL agents**：在任意 environment（single 或 multi-agent）上使用 PPO
- **Creating custom environments**：使用 PufferEnv API
- **Optimizing performance**：面向 parallel environment simulation（vectorization）
- **Integrating existing environments**：来自 Gymnasium、PettingZoo、Atari、Procgen 等
- **Developing policies**：使用 CNN、LSTM 或 custom architectures
- **Scaling RL**：扩展到每秒数百万 steps，以加快 experimentation
- **Multi-agent RL**：使用 native multi-agent environment support

## 核心能力

### 1. High-Performance Training（PuffeRL）

PuffeRL 是 PufferLib 优化的 PPO+LSTM training algorithm，可达到 1M-4M steps/second。

**Quick start training：**
```bash
# CLI training
puffer train procgen-coinrun --train.device cuda --train.learning-rate 3e-4

# Distributed training
torchrun --nproc_per_node=4 train.py
```

**Python training loop：**
```python
import pufferlib
from pufferlib import PuffeRL

# Create vectorized environment
env = pufferlib.make('procgen-coinrun', num_envs=256)

# Create trainer
trainer = PuffeRL(
    env=env,
    policy=my_policy,
    device='cuda',
    learning_rate=3e-4,
    batch_size=32768
)

# Training loop
for iteration in range(num_iterations):
    trainer.evaluate()  # Collect rollouts
    trainer.train()     # Train on batch
    trainer.mean_and_log()  # Log results
```

**关于 comprehensive training guidance**，阅读 `references/training.md`，了解：
- 完整 training workflow 和 CLI options
- 使用 Protein 进行 hyperparameter tuning
- Distributed multi-GPU/multi-node training
- Logger integration（Weights & Biases、Neptune）
- Checkpointing 和 resume training
- Performance optimization tips
- Curriculum learning patterns

### 2. Environment Development（PufferEnv）

使用 PufferEnv API 创建 custom high-performance environments。

**基础 environment structure：**
```python
import numpy as np
from pufferlib import PufferEnv

class MyEnvironment(PufferEnv):
    def __init__(self, buf=None):
        super().__init__(buf)

        # Define spaces
        self.observation_space = self.make_space((4,))
        self.action_space = self.make_discrete(4)

        self.reset()

    def reset(self):
        # Reset state and return initial observation
        return np.zeros(4, dtype=np.float32)

    def step(self, action):
        # Execute action, compute reward, check done
        obs = self._get_observation()
        reward = self._compute_reward()
        done = self._is_done()
        info = {}

        return obs, reward, done, info
```

**使用 template script：** `scripts/env_template.py` 提供完整 single-agent 和 multi-agent environment templates，并包含以下示例：
- 不同 observation space types（vector、image、dict）
- Action space variations（discrete、continuous、multi-discrete）
- Multi-agent environment structure
- Testing utilities

**关于 complete environment development**，阅读 `references/environments.md`，了解：
- PufferEnv API details 和 in-place operation patterns
- Observation 和 action space definitions
- Multi-agent environment creation
- Ocean suite（20+ pre-built environments）
- Performance optimization（Python to C workflow）
- Environment wrappers 和 best practices
- Debugging 和 validation techniques

### 3. Vectorization and Performance

通过 optimized parallel simulation 实现 maximum throughput。

**Vectorization setup：**
```python
import pufferlib

# Automatic vectorization
env = pufferlib.make('environment_name', num_envs=256, num_workers=8)

# Performance benchmarks:
# - Pure Python envs: 100k-500k SPS
# - C-based envs: 100M+ SPS
# - With training: 400k-4M total SPS
```

**关键 optimizations：**
- 用于 zero-copy observation passing 的 shared memory buffers
- 使用 busy-wait flags 替代 pipes/queues
- 用于 async returns 的 surplus environments
- 每个 worker 多个 environments

**关于 vectorization optimization**，阅读 `references/vectorization.md`，了解：
- Architecture 和 performance characteristics
- Worker 和 batch size configuration
- Serial vs multiprocessing vs async modes
- Shared memory 和 zero-copy patterns
- large scale 的 hierarchical vectorization
- Multi-agent vectorization strategies
- Performance profiling 和 troubleshooting

### 4. Policy Development

将 policies 构建为标准 PyTorch modules，并可使用 optional utilities。

**基础 policy structure：**
```python
import torch.nn as nn
from pufferlib.pytorch import layer_init

class Policy(nn.Module):
    def __init__(self, observation_space, action_space):
        super().__init__()

        # Encoder
        self.encoder = nn.Sequential(
            layer_init(nn.Linear(obs_dim, 256)),
            nn.ReLU(),
            layer_init(nn.Linear(256, 256)),
            nn.ReLU()
        )

        # Actor and critic heads
        self.actor = layer_init(nn.Linear(256, num_actions), std=0.01)
        self.critic = layer_init(nn.Linear(256, 1), std=1.0)

    def forward(self, observations):
        features = self.encoder(observations)
        return self.actor(features), self.critic(features)
```

**关于 complete policy development**，阅读 `references/policies.md`，了解：
- 面向 image observations 的 CNN policies
- 带 optimized LSTM 的 recurrent policies（3x faster inference）
- 面向 complex observations 的 multi-input policies
- Continuous action policies
- Multi-agent policies（shared vs independent parameters）
- Advanced architectures（attention、residual）
- Observation normalization 和 gradient clipping
- Policy debugging 和 testing

### 5. Environment Integration

无缝集成来自 popular RL frameworks 的 environments。

**Gymnasium integration：**
```python
import gymnasium as gym
import pufferlib

# Wrap Gymnasium environment
gym_env = gym.make('CartPole-v1')
env = pufferlib.emulate(gym_env, num_envs=256)

# Or use make directly
env = pufferlib.make('gym-CartPole-v1', num_envs=256)
```

**PettingZoo multi-agent：**
```python
# Multi-agent environment
env = pufferlib.make('pettingzoo-knights-archers-zombies', num_envs=128)
```

**Supported frameworks：**
- Gymnasium / OpenAI Gym
- PettingZoo (parallel and AEC)
- Atari (ALE)
- Procgen
- NetHack / MiniHack
- Minigrid
- Neural MMO
- Crafter
- GPUDrive
- MicroRTS
- Griddly
- 以及更多...

**关于 integration details**，阅读 `references/integration.md`，了解：
- 每个 framework 的 complete integration examples
- Custom wrappers（observation、reward、frame stacking、action repeat）
- Space flattening 和 unflattening
- Environment registration
- Compatibility patterns
- Performance considerations
- Integration debugging

## Quick Start Workflow

### 训练 Existing Environments

1. 从 Ocean suite 或 compatible framework 选择 environment
2. 使用 `scripts/train_template.py` 作为起点
3. 为任务配置 hyperparameters
4. 使用 CLI 或 Python script 运行 training
5. 使用 Weights & Biases 或 Neptune 监控
6. 参考 `references/training.md` 进行 optimization

### 创建 Custom Environments

1. 从 `scripts/env_template.py` 开始
2. 定义 observation 和 action spaces
3. 实现 `reset()` 和 `step()` methods
4. 本地测试 environment
5. 使用 `pufferlib.emulate()` 或 `make()` 进行 vectorize
6. 参考 `references/environments.md` 了解 advanced patterns
7. 如有需要，使用 `references/vectorization.md` 优化

### Policy Development

1. 基于 observations 选择 architecture：
   - Vector observations → MLP policy
   - Image observations → CNN policy
   - Sequential tasks → LSTM policy
   - Complex observations → Multi-input policy
2. 使用 `layer_init` 进行合适的 weight initialization
3. 遵循 `references/policies.md` 中的 patterns
4. full training 前先用 environment 测试

### Performance Optimization

1. Profile 当前 throughput（steps per second）
2. 检查 vectorization configuration（num_envs、num_workers）
3. 优化 environment code（in-place ops、numpy vectorization）
4. 对 critical paths 考虑 C implementation
5. 使用 `references/vectorization.md` 进行 systematic optimization

## 资源

### scripts/

**train_template.py** - 完整 training script template，包含：
- Environment creation 和 configuration
- Policy initialization
- Logger integration（WandB、Neptune）
- 带 checkpointing 的 training loop
- Command-line argument parsing
- Multi-GPU distributed training setup

**env_template.py** - Environment implementation templates：
- Single-agent PufferEnv example（grid world）
- Multi-agent PufferEnv example（cooperative navigation）
- Multiple observation/action space patterns
- Testing utilities

### references/

**training.md** - Comprehensive training guide：
- Training workflow 和 CLI options
- Hyperparameter configuration
- Distributed training（multi-GPU、multi-node）
- Monitoring 和 logging
- Checkpointing
- Protein hyperparameter tuning
- Performance optimization
- Common training patterns
- Troubleshooting

**environments.md** - Environment development guide：
- PufferEnv API 和 characteristics
- Observation 和 action spaces
- Multi-agent environments
- Ocean suite environments
- Custom environment development workflow
- Python to C optimization path
- Third-party environment integration
- Wrappers 和 best practices
- Debugging

**vectorization.md** - Vectorization optimization：
- Architecture 和 key optimizations
- Vectorization modes（serial、multiprocessing、async）
- Worker 和 batch configuration
- Shared memory 和 zero-copy patterns
- Advanced vectorization（hierarchical、custom）
- Multi-agent vectorization
- Performance monitoring 和 profiling
- Troubleshooting 和 best practices

**policies.md** - Policy architecture guide：
- Basic policy structure
- CNN policies for images
- LSTM policies with optimization
- Multi-input policies
- Continuous action policies
- Multi-agent policies
- Advanced architectures（attention、residual）
- Observation processing 和 unflattening
- Initialization 和 normalization
- Debugging 和 testing

**integration.md** - Framework integration guide：
- Gymnasium integration
- PettingZoo integration（parallel 和 AEC）
- Third-party environments（Procgen、NetHack、Minigrid 等）
- Custom wrappers（observation、reward、frame stacking 等）
- Space conversion 和 unflattening
- Environment registration
- Compatibility patterns
- Performance considerations
- Debugging integration

## 成功提示

1. **Start simple**：创建 custom environments 前，从 Ocean environments 或 Gymnasium integration 开始

2. **Profile early**：从一开始就测量 steps per second，以识别 bottlenecks

3. **Use templates**：`scripts/train_template.py` 和 `scripts/env_template.py` 提供可靠起点

4. **Read references as needed**：每个 reference file 都是 self-contained，并聚焦特定 capability

5. **Optimize progressively**：从 Python 开始，profile，然后在需要时用 C 优化 critical paths

6. **Leverage vectorization**：PufferLib 的 vectorization 是实现 high throughput 的关键

7. **Monitor training**：使用 WandB 或 Neptune 跟踪 experiments 并及早发现 issues

8. **Test environments**：扩大 training 前验证 environment logic

9. **Check existing environments**：Ocean suite 提供 20+ pre-built environments

10. **Use proper initialization**：policies 始终使用来自 `pufferlib.pytorch` 的 `layer_init`

## 常见 Use Cases

### 在 Standard Benchmarks 上训练
```python
# Atari
env = pufferlib.make('atari-pong', num_envs=256)

# Procgen
env = pufferlib.make('procgen-coinrun', num_envs=256)

# Minigrid
env = pufferlib.make('minigrid-empty-8x8', num_envs=256)
```

### Multi-Agent Learning
```python
# PettingZoo
env = pufferlib.make('pettingzoo-pistonball', num_envs=128)

# Shared policy for all agents
policy = create_policy(env.observation_space, env.action_space)
trainer = PuffeRL(env=env, policy=policy)
```

### Custom Task Development
```python
# Create custom environment
class MyTask(PufferEnv):
    # ... implement environment ...

# Vectorize and train
env = pufferlib.emulate(MyTask, num_envs=256)
trainer = PuffeRL(env=env, policy=my_policy)
```

### High-Performance Optimization
```python
# Maximize throughput
env = pufferlib.make(
    'my-env',
    num_envs=1024,      # Large batch
    num_workers=16,     # Many workers
    envs_per_worker=64  # Optimize per worker
)
```

## 安装

```bash
uv pip install pufferlib
```

## 文档

- Official docs: https://puffer.ai/docs.html
- GitHub: https://github.com/PufferAI/PufferLib
- Discord: 可获得 community support
