# 第一期目标：用 iqoo 12 手机组装 7 英寸 android 掌机

## 用 USB 2.0 接口来有线投屏

* [x] Dell DA100 这款 DisplayLink 设备是否能实现镜像投屏。可以，需要安装 [DisplayLink Presenter](https://www.synaptics.com/cn/products/displaylink-graphics/downloads/android) 这个 android app，然后线接好之后能看到镜像的画面。
* [x] DisplayLink 是否能够双屏异显。可以，用 VLC 播放器验证了。
* [x] 需要验证 DisplayLink 的延迟，对比 scrcpy 延迟。验证了，延迟很好 [latency.md](latency.md)
* [x] 是否 VirtualDisplay 可以开启 android 的 desktop mode。不可以， android 因为安全原因特别限制了。即便是能在第二个Display上启动 activity，各种修改版本的 android 系统的行为差异也特别大，不具有实用性。
* [x] 对比 Silicon Motion 的 InstantView 方案：非常拉跨。

## 去掉投屏的黑边

* [x] 能否拿到 DisplayLink Presenter 创建的 VirtualDisplay。可以拿到这个 display。
* [x] 给 presenter apk 注入一行 log
* [x] 尝试 4k 分辨率：写死了，上不到 4k
* [x] 自动化编译注入的 hook
* [x] 从 image listener 拿到 image plane buffer，并解码成 png 写一份到磁盘上
* [x] 修改 image plane buffer
* [x] 注册 n x 1080 的分辨率，然后裁切 image plane buffer

## 边用边充，一线通

* [x] OTG 线能否同时投屏和充电。已经验证，淘宝关键词：OTG边冲边连U盘移动硬盘转接线。一个typec的公口接 iqoo 12 手机，两个母口（typec或者typea），一个母口是 OTG 口，连接到 DisplayLink 设备，一个母口是供电口。
* [x] 纳米胶是否可以良好固定，方便拆卸。
