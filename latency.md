# DisplayLink 对比 scrcpy 延迟实测

https://rkblog.dev/posts/tech-gadgets/generating-video-display-outputs-usb-displaylink-docking-stations-and-dongles/

![11f7981db33cc985c06e097d9ef2198](https://github.com/user-attachments/assets/acc05163-614d-42b8-a117-e9f98ed43888)

![485d975ce7689bdde4350aa59f2e013](https://github.com/user-attachments/assets/2a08c7b1-f0d3-4bba-a89b-7686dc2767ae)

上面两张是 iqoo12 通过 DisplayLink 投屏的延迟情况。内屏是 144hz 高刷，外屏是 60hz 刷新，屏摄延迟是 8ms。

https://github.com/user-attachments/assets/f72f29b5-af10-459c-bf14-e52d11d458be

上面是 iqoo12 通过 scrcpy 投屏到 windows 笔记本(yoga air 14s 2023)的延迟情况，全程投屏都是快于本地屏幕的。scrcpy 原理是 adb 调试。内屏是 90hz，外屏是 60hz，屏摄延迟是 8ms。

![046dd866a50afdd3bc2081514d5a1b3](https://github.com/user-attachments/assets/d0d5b882-825e-422f-b199-be92fa841d71)

iqoo 12 通过 mirascreen 投屏失败，上面是用 zhangwanmini 通过 mirascreen 投屏到投影仪的延迟情况。mirascreen 的原理是一个单片机在运行 adb 调试。居然也是快于本地屏幕的。内屏是 60 hz，外屏是 60hz，屏摄延迟 11 ms 左右。

![4a4cd428420f764a39256607b0574c0](https://github.com/user-attachments/assets/6bd98bdc-b577-40a1-b0ff-6762ae575c70)

https://github.com/user-attachments/assets/c5416ba5-f4c2-464d-a6e8-e749ec654a5c

上面是 windows 通过 sunshine/moonlight 串流到 iqoo12 然后再通过 DisplayLink 投屏的显示器的延迟情况，这是 5g wifi 加上 DisplayLink 的双重 debuff。内屏是 60hz，外屏是 60hz，屏摄延迟是 8ms。





