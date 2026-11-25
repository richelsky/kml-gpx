# KML / GPX / FIT 轨迹格式转换

纯前端、单文件、不上传服务器。全部解析和转换都在浏览器里跑。

## 支持

| 输入 | 输出 | 说明 |
|---|---|---|
| KML | GPX | `gx:Track`、`LineString`、`Point` |
| GPX | KML | `trk` / `rte` / `wpt` |
| FIT | GPX | Garmin 设备原始数据，提取坐标、海拔、时间戳 |

## 选项

- 合并所有轨迹为一条：把几十上百段 GPS 断点拼成一条连续轨迹
- 删除标注点：丢掉 waypoint，只留线
- 智能合并打卡点为轨迹：应对把轨迹存成一大堆 Point 的 App

## 用法

打开页面，把文件拖进去，勾选选项，点转换。

## 说明

`gx:Track` 是 Google Earth 的扩展命名空间，用 `getElementsByTagName('gx:Track')`
取不到，页面里走的是 `localName` 判断，别改回去。

字体、图标全部本地化，没有任何外部 CDN 依赖，断网也能用。
