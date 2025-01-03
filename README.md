# plug-and-play

给手机加个大屏幕，打造一台即插即玩的游戏掌机。不仅仅是手机，可用一根 usb 线接任意的设备当游戏主机。用到的淘宝买的配件，组装方案以及软件代码均会在这里持续更新，敬请期待。用小红书扫码加入群聊

<img src="https://github.com/user-attachments/assets/cd8d57f7-d7e9-4e3b-b51d-7fb73190d68c" width="200"/>

# 为什么要搞这个项目？

* 无论是 win 掌机还是 android 掌机的 cpu 还在快速更新，买来到手很快就过时了。但是手柄夹屏幕可以用很久都不过时。
* 游戏掌机除了手柄和屏幕，还需要堆足够的散热和电池来满足功耗的要求。这导致了重量很难压下去。
* android 手机太过细长了，拉伸手柄的操控体验没问题，就是屏幕太小，玩游戏费眼睛。
* 适合拉伸手柄的小尺寸平板选择太少了，即便出了小尺寸平板其 cpu 也会比旗舰手机落后一代。而且平板都没有 5g 通信，没法出门串流。也没法代替手机，需要带多套设备。
* vscode remote 非常成熟，开发环境已经可以脱离本地笔记本了。程序员完全可以拿手机接公司的显示器当办公电脑来使用。
* 家里的投影仪，ar眼镜，大屏彩电这些设备都要接一个设备来播放视频。为什么不能接手机，用语音来控制观影？
* 无线串流需要两边开机，还需要给两个设备充电。不如有线连接来得方便。
* 模块可替换，需要大电池，就带大的充电宝。需要更高的性能，就加显卡坞。但是因为手上持握的部分只是屏幕和手柄，并不会影响手感。
* 小尺寸平板据说影响折叠屏的销量。厂商知道你们想要一个大屏，就卖你更高价格的折叠屏。没必要花钱买折叠，三折叠这样的手机来打游戏。

所以当年我购入了老罗锤子的坚果 PRO3 手机来达到上述的目的。现在坚果手机已经没有了，能否用当今的 android 手机，来达到上面的某些需求呢？可能某几款旗舰手机甚至可以一台手机，同时充当高性能掌机，编程开发的pc，以及机顶盒。

同时，目标不仅仅是让 android 手机可以做这个主机设备。windows 迷你小主机，mac mini，显卡坞这些东西也可以当便携主机设备。只要有 usb 口，就可以一线连接，把这个设备转换成一个掌机的形态。

最终的构成是由三部分组成：

* 一套硬件：手柄夹便携屏的硬件，可以连各种设备当掌机。有点类似锤子的 TNT，只是把键盘鼠标换成了手柄
* 一个软件：充分利用旧手机。裁掉 USB 2.0 的 Android 手机通过有线投屏 1080p 的黑边，实现满屏打游戏。这样就不需要限制必须是 usb 3.0 可投屏的设备了。
* 一个软件：充分利用旧手机。实现 android 手机通过 wifi 投 4k 屏跑 ubuntu x86 办公。这个是纯软件的方案，可以不增购任何设备就体验。

百里之行，始于足下

# 第一期目标：用 iqoo 12 手机组装 7 英寸 android 掌机

* 主机：手上的 iqoo 12 手机，只有 usb 2.0 接口，没法直接 typec 连接显示器。
* 便携屏：xequip 用 rog ally 的同款屏幕造的 7 寸便携屏。1920x1080分辨率，120hz刷新率。150克重。由闲鱼购入。
* 拉伸手柄：bsp d10 蓝牙手柄。

第一期目标就是拉伸手柄夹便携屏，然后通过一根 typec 线连接到放口袋里的 iqoo 12 手机，实现 7 寸大屏玩模拟器游戏的体验。[这就需要解决 3 个核心问题](usb2-to-usb3-display.md)

* usb 2.0 怎么投屏显示的问题：不仅仅是 iqoo，很多其他品牌，甚至旗舰机型都阉割 usb 3.0。甚至 xiaomi 14 给你 usb 3.0 也把 desktop mode 给阉割掉了，只有一个屏幕镜像的模式。所以 usb2 的设备也能用非常重要。
* 显示比例的问题：如果是手机 2400x1080 投屏到 1920x1080 的便携屏上会有很大的黑边，无法占满整个 7 寸的屏幕。而且 iqoo 把 adb shell wm resize 也给阉割了，改分辨率只是拉伸的效果。
* 一线通的问题：手柄如果要单独通过蓝牙去接手机，那么换设备就需要重新配对。而且蓝牙手柄还要独立充电。如何能够做到一线通，把充电，连显示器，连手柄这三件事情都搞定。


## 一期目标达成

https://www.bilibili.com/video/BV1SbS2YVEkV/ 效果见视频

* 发布源代码
* ipad 改的便携屏分辨率会有拉伸
* equip和ipad两款便携屏的触屏在横屏下都是错的
* 虽然和所有的displaylink都兼容，但是这款 hdmi to typec 转接之后就是没声音了

USB2.0转USB3.0视频输出拓展坞，配件清单，合计 398.1 元。特别注意 ULT-unite hdmi转typec 是关键组件，试过了3款其他的拓展坞均无法适配。

| 图片 | 名称 | 价格 |
| --- | --- | --- |
| <img src="https://github.com/user-attachments/assets/2720b5f1-850e-4354-b057-7a943126a68e" width="200"/>| ORICO 10合1 DisplayLink 扩展坞 | 闲鱼 211 | 
| <img src="https://github.com/user-attachments/assets/5782a869-481e-4671-af53-7252a2ede8ef" width="200"/> | ULT-unite hdmi转typec | 淘宝 118 |
| <img src="https://github.com/user-attachments/assets/bf026c08-a4d0-4d9b-8a75-5853b0840638" width="200"/> | OTG 边充边连U盘移动硬盘转接线 | 淘宝 31.9 |
| <img src="https://github.com/user-attachments/assets/64c73948-a00a-4ca7-b260-9e34e4b5808b" width="200"/> | 得力纳米双面胶 | 淘宝 37.2 |

可多场景复用得便携屏掌机，配件清单，合计 1238。可接手机，电脑。

| 图片 | 名称 | 价格 |
| --- | --- | --- |
| <img src="https://github.com/user-attachments/assets/6b1960c0-d475-4c02-b6b0-7cd7d903eaea" width="200"/> | equip 7寸 ROG Ally 同款屏 | 闲鱼 999 |
| <img src="https://github.com/user-attachments/assets/b2512a8d-42ba-4a5f-810f-f3a885cf27d3" width="200"/> | 5孔螺丝，joycon 滑轨 | 闲鱼 20 |
| <img src="https://github.com/user-attachments/assets/4f27f4a3-669c-4b2f-bd9a-c5a01ff70ad6" width="200"/> | 良值机甲分体式手柄 | 闲鱼 180 |
| <img src="https://github.com/user-attachments/assets/920fea6b-dab7-44ca-b931-7b575f66db50" width="200"/> | 魔派joycon二合一电脑接收器 | 拼多多 39 |

# 第二期目标：修复掌机的触控

用 usb otg 获得触摸屏的数据，然后用 accessibility service 进行回放

* [x] 获得触摸数据
* [ ] 获得点击数据
* [ ] accessibility service 回放
* [ ] 跟随内屏转向
* [ ] 自动检测黑边
