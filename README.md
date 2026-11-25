# KML / GPX / FIT 轨迹格式转换

轨迹文件互转的纯静态单页工具，解析和转换全在浏览器里跑，文件不上传服务器。

在线访问：https://richelsky.github.io/kml-gpx/converter.html

- `converter.html` 页面本体，逻辑、样式、图标全部内联，零外部依赖，可离线打开
- `index.html` 根路径跳转，访问 https://richelsky.github.io/kml-gpx/ 也能进

## 怎么用

打开页面，把 `.kml` / `.gpx` / `.fit` 拖进上传区，勾选需要的选项，点转换，直接下载。

三个选项：

合并所有轨迹为一条，把几十上百段 GPS 断点拼成一条连续轨迹，长按暂停、丢信号的轨迹必须开这个。

删除标注点，只留线，不要 waypoint。

智能合并打卡点为轨迹，应对把轨迹存成一大堆 Point 的 App。

## 支持

KML 转 GPX，认 `gx:Track`、`LineString`、`Point`。

GPX 转 KML，认 `trk` / `rte` / `wpt`。

FIT 转 GPX，认 Garmin 设备原始数据，提取坐标、海拔、时间戳。

`gx:Track` 属于 Google Earth 扩展命名空间，`getElementsByTagName('gx:Track')` 取不到，
页面里走 `localName` 判断，改代码时别动回去。

无第三方素材，无版权问题。
