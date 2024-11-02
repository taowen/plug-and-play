# DisplayLink 延迟实测

另外一份延迟测试 https://rkblog.dev/posts/tech-gadgets/generating-video-display-outputs-usb-displaylink-docking-stations-and-dongles/

测试使用的设备

* 主机：iqoo 12，usb 2.0 接口，内屏 144hz 高刷新
* 显示器：DELL，60hz 刷新
* 分辨率：1920 x 1080

| 品牌型号 | 芯片 | Android端 | 两次测量值 |
| --- | --- | --- | --- | 
| Wavlink WL-UG7601HC | SiliconMotion SM768 无需供电 | SMI Instant View | 72ms, 83ms |
| ORICO DPL-10 | DisplayLink 型号不详 无需供电 | DisplayLink Presenter | 45ms, 36ms |
| 海备思 DPL01 | DisplayLink DL-6950 无需供电 | DisplayLink Presenter | 27ms, 27ms |
| DELL DA100 | DisplayLink DL-3xxx 需要供电 | DisplayLink Presenter | 36ms, 36ms |

结论：海备思的 DPL01 延迟最低，所有的 DisplayLink 都比 SiliconMotion 要低。

## Silion Motion

![22f73cd802a7bc66dba69c688176a74](https://github.com/user-attachments/assets/4475f887-fcb4-4fab-9ac5-be972c0a3d79)

![3523fd470f35d4b8be48e1efeaf75d6](https://github.com/user-attachments/assets/8f9cca96-1083-4747-8097-c8eb4ebb00bc)

## Orico

![2e68f8fcabbd09cf5dec8a4ae1a2034](https://github.com/user-attachments/assets/40c0682f-3cd9-4907-aa94-a9174f93215e)


![0c8759487af2fb570e2d45859110b15](https://github.com/user-attachments/assets/76d2c238-5051-47c0-ab9d-e8916cdb7fb6)

# 海备思

![58bef6b5803f0a92c15214e39a4e65e](https://github.com/user-attachments/assets/e5d0eb45-c030-405e-b142-ab60c742293c)

![f508579e4a1cb2799acf73925cbabfc](https://github.com/user-attachments/assets/ff50cb0b-ba77-47b6-a4d4-6c41d7565af4)

# DELL DA100

![37c984c8bc7b58180fab4455d368499](https://github.com/user-attachments/assets/9e0e991d-db0b-4d17-8a9b-d0070ab92ddb)

![f2845a01731f2e3a1645651673817f6](https://github.com/user-attachments/assets/417037e2-c44f-4739-b89e-93dbc76c2400)

