---
name: geopandas
description: 用于处理 geospatial vector data 的 Python library，包括 shapefiles、GeoJSON 和 GeoPackage files。处理 geographic data 以进行 spatial analysis、geometric operations、coordinate transformations、spatial joins、overlay operations、choropleth mapping，或任何涉及读取/写入/分析 vector geographic data 的任务时使用。支持 PostGIS databases、interactive maps，以及与 matplotlib/folium/cartopy 集成。用于 buffer analysis、datasets 之间的 spatial joins、dissolving boundaries、clipping data、计算 areas/distances、reprojecting coordinate systems、创建 maps，或在 spatial file formats 之间转换等任务。
license: BSD-3-Clause license
metadata:
    skill-author: K-Dense Inc.
---

# GeoPandas

GeoPandas 扩展 pandas，使其可以对 geometric types 执行 spatial operations。它结合了 pandas 和 shapely 的能力，用于 geospatial data analysis。

## 安装

```bash
uv pip install geopandas
```

### Optional Dependencies

```bash
# For interactive maps
uv pip install folium

# For classification schemes in mapping
uv pip install mapclassify

# For faster I/O operations (2-4x speedup)
uv pip install pyarrow

# For PostGIS database support
uv pip install psycopg2
uv pip install geoalchemy2

# For basemaps
uv pip install contextily

# For cartographic projections
uv pip install cartopy
```

## Quick Start

```python
import geopandas as gpd

# Read spatial data
gdf = gpd.read_file("data.geojson")

# Basic exploration
print(gdf.head())
print(gdf.crs)
print(gdf.geometry.geom_type)

# Simple plot
gdf.plot()

# Reproject to different CRS
gdf_projected = gdf.to_crs("EPSG:3857")

# Calculate area (use projected CRS for accuracy)
gdf_projected['area'] = gdf_projected.geometry.area

# Save to file
gdf.to_file("output.gpkg")
```

## 核心概念

### Data Structures

- **GeoSeries**：带 spatial operations 的 geometries vector
- **GeoDataFrame**：带 geometry column 的 tabular data structure

详情见 [data-structures.md](references/data-structures.md)。

### 读取和写入数据

GeoPandas 可读写多种格式：Shapefile、GeoJSON、GeoPackage、PostGIS、Parquet。

```python
# Read with filtering
gdf = gpd.read_file("data.gpkg", bbox=(xmin, ymin, xmax, ymax))

# Write with Arrow acceleration
gdf.to_file("output.gpkg", use_arrow=True)
```

综合 I/O operations 见 [data-io.md](references/data-io.md)。

### Coordinate Reference Systems

始终检查和管理 CRS，以保证 spatial operations 准确：

```python
# Check CRS
print(gdf.crs)

# Reproject (transforms coordinates)
gdf_projected = gdf.to_crs("EPSG:3857")

# Set CRS (only when metadata missing)
gdf = gdf.set_crs("EPSG:4326")
```

CRS operations 见 [crs-management.md](references/crs-management.md)。

## 常见操作

### Geometric Operations

Buffer、simplify、centroid、convex hull、affine transformations：

```python
# Buffer by 10 units
buffered = gdf.geometry.buffer(10)

# Simplify with tolerance
simplified = gdf.geometry.simplify(tolerance=5, preserve_topology=True)

# Get centroids
centroids = gdf.geometry.centroid
```

所有 operations 见 [geometric-operations.md](references/geometric-operations.md)。

### Spatial Analysis

Spatial joins、overlay operations、dissolve：

```python
# Spatial join (intersects)
joined = gpd.sjoin(gdf1, gdf2, predicate='intersects')

# Nearest neighbor join
nearest = gpd.sjoin_nearest(gdf1, gdf2, max_distance=1000)

# Overlay intersection
intersection = gpd.overlay(gdf1, gdf2, how='intersection')

# Dissolve by attribute
dissolved = gdf.dissolve(by='region', aggfunc='sum')
```

Analysis operations 见 [spatial-analysis.md](references/spatial-analysis.md)。

### Visualization

创建 static 和 interactive maps：

```python
# Choropleth map
gdf.plot(column='population', cmap='YlOrRd', legend=True)

# Interactive map
gdf.explore(column='population', legend=True).save('map.html')

# Multi-layer map
import matplotlib.pyplot as plt
fig, ax = plt.subplots()
gdf1.plot(ax=ax, color='blue')
gdf2.plot(ax=ax, color='red')
```

Mapping techniques 见 [visualization.md](references/visualization.md)。

## 详细文档

- **[Data Structures](references/data-structures.md)** - GeoSeries 和 GeoDataFrame fundamentals
- **[Data I/O](references/data-io.md)** - Reading/writing files、PostGIS、Parquet
- **[Geometric Operations](references/geometric-operations.md)** - Buffer、simplify、affine transforms
- **[Spatial Analysis](references/spatial-analysis.md)** - Joins、overlay、dissolve、clipping
- **[Visualization](references/visualization.md)** - Plotting、choropleth maps、interactive maps
- **[CRS Management](references/crs-management.md)** - Coordinate reference systems 和 projections

## 常见工作流

### Load, Transform, Analyze, Export

```python
# 1. Load data
gdf = gpd.read_file("data.shp")

# 2. Check and transform CRS
print(gdf.crs)
gdf = gdf.to_crs("EPSG:3857")

# 3. Perform analysis
gdf['area'] = gdf.geometry.area
buffered = gdf.copy()
buffered['geometry'] = gdf.geometry.buffer(100)

# 4. Export results
gdf.to_file("results.gpkg", layer='original')
buffered.to_file("results.gpkg", layer='buffered')
```

### Spatial Join and Aggregate

```python
# Join points to polygons
points_in_polygons = gpd.sjoin(points_gdf, polygons_gdf, predicate='within')

# Aggregate by polygon
aggregated = points_in_polygons.groupby('index_right').agg({
    'value': 'sum',
    'count': 'size'
})

# Merge back to polygons
result = polygons_gdf.merge(aggregated, left_index=True, right_index=True)
```

### Multi-Source Data Integration

```python
# Read from different sources
roads = gpd.read_file("roads.shp")
buildings = gpd.read_file("buildings.geojson")
parcels = gpd.read_postgis("SELECT * FROM parcels", con=engine, geom_col='geom')

# Ensure matching CRS
buildings = buildings.to_crs(roads.crs)
parcels = parcels.to_crs(roads.crs)

# Perform spatial operations
buildings_near_roads = buildings[buildings.geometry.distance(roads.union_all()) < 50]
```

## Performance Tips

1. **使用 spatial indexing**：GeoPandas 会为大多数 operations 自动创建 spatial indexes
2. **读取时过滤**：使用 `bbox`、`mask` 或 `where` 参数只加载所需数据
3. **I/O 使用 Arrow**：添加 `use_arrow=True` 可让读写快 2-4 倍
4. **Simplify geometries**：当 precision 不关键时，使用 `.simplify()` 降低复杂度
5. **Batch operations**：Vectorized operations 远快于逐行迭代
6. **使用合适 CRS**：area/distance 用 projected CRS，visualization 用 geographic

## 最佳实践

1. Spatial operations 前**始终检查 CRS**
2. Area 和 distance calculations 使用 **projected CRS**
3. Spatial joins 或 overlays 前**匹配 CRS**
4. Operations 前用 `.is_valid` **验证 geometries**
5. 修改 geometry columns 时使用 `.copy()`，避免 side effects
6. 为 analysis 简化时保留 topology
7. 现代 workflows 使用 GeoPackage format（优于 Shapefile）
8. 在 sjoin_nearest 中设置 max_distance 以提升性能
