---
name: opentrons-integration
description: 面向 OT-2 和 Flex 机器人的官方 Opentrons Protocol API。用于为 Opentrons 硬件编写协议，并完整访问 Protocol API v2 功能。最适合生产级 Opentrons 协议和官方 API 兼容性。若需要多厂商自动化或更广泛的设备控制，请使用 pylabrobot。
license: Unknown
metadata:
    skill-author: K-Dense Inc.
---

# Opentrons 集成

## 概述

Opentrons 是一个基于 Python 的实验室自动化平台，面向 Flex 和 OT-2 机器人。编写 Protocol API v2 协议，用于液体处理、控制硬件模块（heater-shaker、thermocycler）、管理 labware，并实现自动化移液工作流。

## 何时使用此 Skill

在以下情况应使用此 skill：
- 使用 Python 编写 Opentrons Protocol API v2 协议
- 在 Flex 或 OT-2 机器人上自动化液体处理工作流
- 控制硬件模块（temperature、magnetic、heater-shaker、thermocycler）
- 设置 labware 配置和 deck 布局
- 实现复杂移液操作（连续稀释、板复制、PCR 设置）
- 管理吸头使用并优化协议效率
- 使用多通道移液器进行 96-well plate 操作
- 在机器人执行前模拟和测试协议

## 核心能力

### 1. 协议结构和 Metadata

每个 Opentrons 协议都遵循标准结构：

```python
from opentrons import protocol_api

# Metadata
metadata = {
    'protocolName': 'My Protocol',
    'author': 'Name <email@example.com>',
    'description': 'Protocol description',
    'apiLevel': '2.19'  # Use latest available API version
}

# Requirements (optional)
requirements = {
    'robotType': 'Flex',  # or 'OT-2'
    'apiLevel': '2.19'
}

# Run function
def run(protocol: protocol_api.ProtocolContext):
    # Protocol commands go here
    pass
```

**关键元素：**
- 导入 `protocol_api`，来源为 `opentrons`
- 定义包含 protocolName、author、description、apiLevel 的 `metadata` dict
- 可选的 `requirements` dict，用于机器人类型和 API 版本
- 实现 `run()` 函数，并接收 `ProtocolContext` 作为参数
- 所有协议逻辑都放在 `run()` 函数内

### 2. 加载硬件

**加载仪器（移液器）：**

```python
def run(protocol: protocol_api.ProtocolContext):
    # Load pipette on specific mount
    left_pipette = protocol.load_instrument(
        'p1000_single_flex',  # Instrument name
        'left',               # Mount: 'left' or 'right'
        tip_racks=[tip_rack]  # List of tip rack labware objects
    )
```

常见移液器名称：
- Flex: `p50_single_flex`, `p1000_single_flex`, `p50_multi_flex`, `p1000_multi_flex`
- OT-2: `p20_single_gen2`, `p300_single_gen2`, `p1000_single_gen2`, `p20_multi_gen2`, `p300_multi_gen2`

**加载 Labware：**

```python
# Load labware directly on deck
plate = protocol.load_labware(
    'corning_96_wellplate_360ul_flat',  # Labware API name
    'D1',                                # Deck slot (Flex: A1-D3, OT-2: 1-11)
    label='Sample Plate'                 # Optional display label
)

# Load tip rack
tip_rack = protocol.load_labware('opentrons_flex_96_tiprack_1000ul', 'C1')

# Load labware on adapter
adapter = protocol.load_adapter('opentrons_flex_96_tiprack_adapter', 'B1')
tips = adapter.load_labware('opentrons_flex_96_tiprack_200ul')
```

**加载模块：**

```python
# Temperature module
temp_module = protocol.load_module('temperature module gen2', 'D3')
temp_plate = temp_module.load_labware('corning_96_wellplate_360ul_flat')

# Magnetic module
mag_module = protocol.load_module('magnetic module gen2', 'C2')
mag_plate = mag_module.load_labware('nest_96_wellplate_100ul_pcr_full_skirt')

# Heater-Shaker module
hs_module = protocol.load_module('heaterShakerModuleV1', 'D1')
hs_plate = hs_module.load_labware('corning_96_wellplate_360ul_flat')

# Thermocycler module (takes up specific slots automatically)
tc_module = protocol.load_module('thermocyclerModuleV2')
tc_plate = tc_module.load_labware('nest_96_wellplate_100ul_pcr_full_skirt')
```

### 3. 液体处理操作

**基本操作：**

```python
# Pick up tip
pipette.pick_up_tip()

# Aspirate (draw liquid in)
pipette.aspirate(
    volume=100,           # Volume in µL
    location=source['A1'] # Well or location object
)

# Dispense (expel liquid)
pipette.dispense(
    volume=100,
    location=dest['B1']
)

# Drop tip
pipette.drop_tip()

# Return tip to rack
pipette.return_tip()
```

**复杂操作：**

```python
# Transfer (combines pick_up, aspirate, dispense, drop_tip)
pipette.transfer(
    volume=100,
    source=source_plate['A1'],
    dest=dest_plate['B1'],
    new_tip='always'  # 'always', 'once', or 'never'
)

# Distribute (one source to multiple destinations)
pipette.distribute(
    volume=50,
    source=reservoir['A1'],
    dest=[plate['A1'], plate['A2'], plate['A3']],
    new_tip='once'
)

# Consolidate (multiple sources to one destination)
pipette.consolidate(
    volume=50,
    source=[plate['A1'], plate['A2'], plate['A3']],
    dest=reservoir['A1'],
    new_tip='once'
)
```

**高级技术：**

```python
# Mix (aspirate and dispense in same location)
pipette.mix(
    repetitions=3,
    volume=50,
    location=plate['A1']
)

# Air gap (prevent dripping)
pipette.aspirate(100, source['A1'])
pipette.air_gap(20)  # 20µL air gap
pipette.dispense(120, dest['A1'])

# Blow out (expel remaining liquid)
pipette.blow_out(location=dest['A1'].top())

# Touch tip (remove droplets on tip exterior)
pipette.touch_tip(location=plate['A1'])
```

**流速控制：**

```python
# Set flow rates (µL/s)
pipette.flow_rate.aspirate = 150
pipette.flow_rate.dispense = 300
pipette.flow_rate.blow_out = 400
```

### 4. 访问孔位和位置

**孔位访问方法：**

```python
# By name
well_a1 = plate['A1']

# By index
first_well = plate.wells()[0]

# All wells
all_wells = plate.wells()  # Returns list

# By rows
rows = plate.rows()  # Returns list of lists
row_a = plate.rows()[0]  # All wells in row A

# By columns
columns = plate.columns()  # Returns list of lists
column_1 = plate.columns()[0]  # All wells in column 1

# Wells by name (dictionary)
wells_dict = plate.wells_by_name()  # {'A1': Well, 'A2': Well, ...}
```

**位置方法：**

```python
# Top of well (default: 1mm below top)
pipette.aspirate(100, well.top())
pipette.aspirate(100, well.top(z=5))  # 5mm above top

# Bottom of well (default: 1mm above bottom)
pipette.aspirate(100, well.bottom())
pipette.aspirate(100, well.bottom(z=2))  # 2mm above bottom

# Center of well
pipette.aspirate(100, well.center())
```

### 5. 硬件模块控制

**Temperature Module：**

```python
# Set temperature
temp_module.set_temperature(celsius=4)

# Wait for temperature
temp_module.await_temperature(celsius=4)

# Deactivate
temp_module.deactivate()

# Check status
current_temp = temp_module.temperature  # Current temperature
target_temp = temp_module.target  # Target temperature
```

**Magnetic Module：**

```python
# Engage (raise magnets)
mag_module.engage(height_from_base=10)  # mm from labware base

# Disengage (lower magnets)
mag_module.disengage()

# Check status
is_engaged = mag_module.status  # 'engaged' or 'disengaged'
```

**Heater-Shaker Module：**

```python
# Set temperature
hs_module.set_target_temperature(celsius=37)

# Wait for temperature
hs_module.wait_for_temperature()

# Set shake speed
hs_module.set_and_wait_for_shake_speed(rpm=500)

# Close labware latch
hs_module.close_labware_latch()

# Open labware latch
hs_module.open_labware_latch()

# Deactivate heater
hs_module.deactivate_heater()

# Deactivate shaker
hs_module.deactivate_shaker()
```

**Thermocycler Module：**

```python
# Open lid
tc_module.open_lid()

# Close lid
tc_module.close_lid()

# Set lid temperature
tc_module.set_lid_temperature(celsius=105)

# Set block temperature
tc_module.set_block_temperature(
    temperature=95,
    hold_time_seconds=30,
    hold_time_minutes=0.5,
    block_max_volume=50  # µL per well
)

# Execute profile (PCR cycling)
profile = [
    {'temperature': 95, 'hold_time_seconds': 30},
    {'temperature': 57, 'hold_time_seconds': 30},
    {'temperature': 72, 'hold_time_seconds': 60}
]
tc_module.execute_profile(
    steps=profile,
    repetitions=30,
    block_max_volume=50
)

# Deactivate
tc_module.deactivate_lid()
tc_module.deactivate_block()
```

**Absorbance Plate Reader：**

```python
# Initialize and read
result = plate_reader.read(wavelengths=[450, 650])

# Access readings
absorbance_data = result  # Dict with wavelength keys
```

### 6. 液体跟踪和标记

**定义液体：**

```python
# Define liquid types
water = protocol.define_liquid(
    name='Water',
    description='Ultrapure water',
    display_color='#0000FF'  # Hex color code
)

sample = protocol.define_liquid(
    name='Sample',
    description='Cell lysate sample',
    display_color='#FF0000'
)
```

**将液体加载到孔位：**

```python
# Load liquid into specific wells
reservoir['A1'].load_liquid(liquid=water, volume=50000)  # µL
plate['A1'].load_liquid(liquid=sample, volume=100)

# Mark wells as empty
plate['B1'].load_empty()
```

### 7. 协议控制和实用工具

**执行控制：**

```python
# Pause protocol
protocol.pause(msg='Replace tip box and resume')

# Delay
protocol.delay(seconds=60)
protocol.delay(minutes=5)

# Comment (appears in logs)
protocol.comment('Starting serial dilution')

# Home robot
protocol.home()
```

**条件逻辑：**

```python
# Check if simulating
if protocol.is_simulating():
    protocol.comment('Running in simulation mode')
else:
    protocol.comment('Running on actual robot')
```

**Rail Lights（仅 Flex）：**

```python
# Turn lights on
protocol.set_rail_lights(on=True)

# Turn lights off
protocol.set_rail_lights(on=False)
```

### 8. 多通道和 8 通道移液

使用多通道移液器时：

```python
# Load 8-channel pipette
multi_pipette = protocol.load_instrument(
    'p300_multi_gen2',
    'left',
    tip_racks=[tips]
)

# Access entire column with single well reference
multi_pipette.transfer(
    volume=100,
    source=source_plate['A1'],  # Accesses entire column 1
    dest=dest_plate['A1']       # Dispenses to entire column 1
)

# Use rows() for row-wise operations
for row in plate.rows():
    multi_pipette.transfer(100, reservoir['A1'], row[0])
```

### 9. 常见协议模式

**连续稀释：**

```python
def run(protocol: protocol_api.ProtocolContext):
    # Load labware
    tips = protocol.load_labware('opentrons_flex_96_tiprack_200ul', 'D1')
    reservoir = protocol.load_labware('nest_12_reservoir_15ml', 'D2')
    plate = protocol.load_labware('corning_96_wellplate_360ul_flat', 'D3')

    # Load pipette
    p300 = protocol.load_instrument('p300_single_flex', 'left', tip_racks=[tips])

    # Add diluent to all wells except first
    p300.transfer(100, reservoir['A1'], plate.rows()[0][1:])

    # Serial dilution across row
    p300.transfer(
        100,
        plate.rows()[0][:11],  # Source: wells 0-10
        plate.rows()[0][1:],   # Dest: wells 1-11
        mix_after=(3, 50),     # Mix 3x with 50µL after dispense
        new_tip='always'
    )
```

**板复制：**

```python
def run(protocol: protocol_api.ProtocolContext):
    # Load labware
    tips = protocol.load_labware('opentrons_flex_96_tiprack_1000ul', 'C1')
    source = protocol.load_labware('corning_96_wellplate_360ul_flat', 'D1')
    dest = protocol.load_labware('corning_96_wellplate_360ul_flat', 'D2')

    # Load pipette
    p1000 = protocol.load_instrument('p1000_single_flex', 'left', tip_racks=[tips])

    # Transfer from all wells in source to dest
    p1000.transfer(
        100,
        source.wells(),
        dest.wells(),
        new_tip='always'
    )
```

**PCR 设置：**

```python
def run(protocol: protocol_api.ProtocolContext):
    # Load thermocycler
    tc_mod = protocol.load_module('thermocyclerModuleV2')
    tc_plate = tc_mod.load_labware('nest_96_wellplate_100ul_pcr_full_skirt')

    # Load tips and reagents
    tips = protocol.load_labware('opentrons_flex_96_tiprack_200ul', 'C1')
    reagents = protocol.load_labware('opentrons_24_tuberack_nest_1.5ml_snapcap', 'D1')

    # Load pipette
    p300 = protocol.load_instrument('p300_single_flex', 'left', tip_racks=[tips])

    # Open thermocycler lid
    tc_mod.open_lid()

    # Distribute master mix
    p300.distribute(
        20,
        reagents['A1'],
        tc_plate.wells(),
        new_tip='once'
    )

    # Add samples (example for first 8 wells)
    for i, well in enumerate(tc_plate.wells()[:8]):
        p300.transfer(5, reagents.wells()[i+1], well, new_tip='always')

    # Run PCR
    tc_mod.close_lid()
    tc_mod.set_lid_temperature(105)

    # PCR profile
    tc_mod.set_block_temperature(95, hold_time_seconds=180)

    profile = [
        {'temperature': 95, 'hold_time_seconds': 15},
        {'temperature': 60, 'hold_time_seconds': 30},
        {'temperature': 72, 'hold_time_seconds': 30}
    ]
    tc_mod.execute_profile(steps=profile, repetitions=35, block_max_volume=25)

    tc_mod.set_block_temperature(72, hold_time_minutes=5)
    tc_mod.set_block_temperature(4)

    tc_mod.deactivate_lid()
    tc_mod.open_lid()
```

## 最佳实践

1. **始终指定 API level**：在 metadata 中使用最新稳定 API 版本
2. **使用有意义的标签**：为 labware 添加标签，便于在日志中识别
3. **检查吸头可用性**：确保有足够吸头完成协议
4. **添加注释**：使用 `protocol.comment()` 进行调试和日志记录
5. **先模拟**：在机器人上运行前始终先在模拟中测试协议
6. **优雅处理错误**：需要人工干预时添加暂停
7. **考虑时间安排**：协议需要孵育周期时使用延迟
8. **跟踪液体**：使用液体跟踪以获得更好的设置验证
9. **优化吸头使用**：适当使用 `new_tip='once'` 以节省吸头
10. **控制流速**：针对黏性或挥发性液体调整流速

## 故障排查

**常见问题：**

- **吸头不足**：验证 tip rack 容量符合协议要求
- **Labware 碰撞**：检查 deck 布局是否存在空间冲突
- **体积错误**：确保体积不超过孔位或移液器容量
- **模块无响应**：验证模块连接正确且 firmware 已更新
- **体积不准确**：校准移液器并检查是否有气泡
- **协议在模拟中失败**：检查 API 版本兼容性和 labware 定义

## 资源

有关详细 API 文档，请参见此 skill 目录中的 `references/api_reference.md`。

有关示例协议模板，请参见 `scripts/` 目录。
