# plug-and-play

给手机加个大屏幕，打造一台即插即玩的游戏掌机。不仅仅是手机，可用一根 usb 线接任意的设备当游戏主机。用到的淘宝买的配件，组装方案以及软件代码均会在这里持续更新，敬请期待。用小红书扫码加入群聊

![0c9536c33812b0cff6d10ca764ce648](https://github.com/user-attachments/assets/cd8d57f7-d7e9-4e3b-b51d-7fb73190d68c)

# 目标

为什么要搞这个项目？

* 游戏掌机除了手柄和屏幕，还需要堆足够的散热和电池来满足功耗的要求。这导致了重量很难压下去。
* android 手机太过细长了，拉伸手柄的操控体验没问题，就是屏幕太小，玩游戏费眼睛。
* 适合拉伸手柄的小尺寸平板选择太少了，即便出了小尺寸平板其 cpu 也会比旗舰手机落后一代。而且平板都没有 5g 通信，没法出门串流。也没法代替手机，需要带多套设备。
* vscode remote 非常成熟，开发环境已经可以脱离本地笔记本了。程序员完全可以拿手机接公司的显示器当办公电脑来使用。
* 家里的投影仪，ar眼镜，大屏彩电这些设备都要接一个设备来播放视频。为什么不能接手机，用语音来控制观影？
* 无线串流需要两边开机，还需要给两个设备充电。不如有线连接来得方便。
* 模块可替换，需要大电池，就带大的充电宝。需要更高的性能，就加显卡坞。不会因为每出一代新的cpu，都要等着掌机厂商，或者小尺寸平板厂商卖一台全新的设备。
* 小尺寸平板据说影响折叠屏的销量。厂商知道你们想要一个大屏，就卖你更高价格的折叠屏。没必要花钱买折叠，三折叠这样的手机来打游戏。

所以当年我购入了坚果 R2 手机来达到上述的目的。现在坚果手机已经没有了，能否用当今的 android 手机，来达到上面的某些需求呢？可能某几款旗舰手机甚至可以一台手机，同时充当高性能掌机，编程开发的pc，以及机顶盒。

同时，目标不仅仅是让 android 手机可以做这个主机设备。windows 迷你小主机，mac mini，显卡坞这些东西也可以当便携主机设备。只要有 usb 口，就可以一线连接，把这个设备转换成一个掌机的形态。

其形态和锤子的 TNT 是很类似的，只是把键盘鼠标换成了手柄。从办公为目标，变成了握持屏幕打游戏为目标。

# 第一期目标

* 主机：手上的 iqoo 12 手机，只有 usb 2.0 接口，没法直接 typec 连接显示器。如果要求必须有全功能 usb3 typec 口，就像锤子 TNT 那样就受众太小了。
* 便携屏：xequip 的 7 寸便携屏。1920x1080分辨率，120hz刷新率。rog ally 的同款屏幕。150克重。由闲鱼购入。
* 拉伸手柄：bsp d10 蓝牙手柄。

第一期目标就是拉伸手柄夹便携屏，然后通过一根 typec 线连接到放口袋里的 iqoo 12 手机，实现 7 寸大屏玩模拟器游戏的体验。这就需要解决 3 个核心问题

* usb 2.0 怎么投屏显示的问题：不仅仅是 iqoo，很多其他品牌，甚至旗舰机型都阉割 usb 3.0。甚至 xiaomi 14 给你 usb 3.0 也把 desktop mode 给阉割掉了，只有一个屏幕镜像的模式。所以 usb2 的设备也能用非常重要。
* 显示比例的问题：如果是手机 2400x1080 投屏到 1920x1080 的便携屏上会有很大的黑边，无法占满整个 7 寸的屏幕。而且 iqoo 把 adb shell wm resize 也给阉割了，改分辨率只是拉伸的效果。
* 一线通的问题：手柄如果要单独通过蓝牙去接手机，那么换设备就需要重新配对。而且蓝牙手柄还要独立充电。如何能够做到一线通，把充电，连显示器，连手柄这三件事情都搞定。

对这三个方案目前的技术选型是用 DisplayLink 来解决 usb 2.0 的投屏问题。用 android 的 Presentation API 写一个 app 来解决显示比例的问题。用一个扩展坞来把手柄和屏幕连接到一起。最后一根 typec 线把扩展坞和手机与电池连接。

## DisplayLink 的可行性验证

* [x] Dell DA100 这款 DisplayLink 设备是否能实现镜像投屏。可以，需要安装 [DisplayLink Presenter](https://www.synaptics.com/cn/products/displaylink-graphics/downloads/android) 这个 android app，然后线接好之后能看到镜像的画面。
* [x] DisplayLink 是否能够双屏异显。可以，用 VLC 播放器验证了。
* [x] 需要验证 DisplayLink 的延迟，对比 scrcpy 延迟。验证了，延迟很好 [latency.md](latency.md)
* [ ] 是否 VirtualDisplay 可以开启 android 的 desktop mode。

## Presentation API 的可行性验证

* [ ] 能否拿到 DisplayLink Presenter 创建的 VirtualDisplay
* [ ] 用 Presentation 能不能把 winlator 的游戏界面按 16:9 的比例投到便携屏上。

## 一线通的可行性验证

* [x] OTG 线能否同时投屏和充电。已经验证，淘宝关键词：OTG边冲边连U盘移动硬盘转接线。一个typec的公口接 iqoo 12 手机，两个母口（typec或者typea），一个母口是 OTG 口，连接到 DisplayLink 设备，一个母口是供电口。
* [ ] 纳米胶是否可以良好固定，方便拆卸。
