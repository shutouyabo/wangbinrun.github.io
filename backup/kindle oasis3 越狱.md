最近用kindle7的看书，由于这款没有屏幕灯，看书不太方便，随即想把另一个kindle oasis 3越狱下。书伴网上推荐的，显示广告后进行越狱，这个方式我没有把广告调试显示出来，搜易这个方式行不通。

早上给淘宝卖家询问了下，也是需要邮寄给他，他再进行越狱后，再邮寄回来，这个方式特麻烦，先不说时间问题，光是设备的风险也不好控。

突然询问下豆包，看会不会给一些不一样的大案，果然根据豆包给的步骤，不需要显示出广告，一步一步做下去，越狱成功。


我问：我还有一个 Kindle Oasis 第十代。我的版本是 Kindle 5.18.2。我想把这个也越狱，装 KOReader 这个软件，询问怎么进行越狱？

豆包：

你的设备：Kindle Oasis 3（KO3，第 10 代）

固件：5.18.2 ✅

可以越狱！ 用 Nosebleed 越狱法 （2026 最新，支持 5.16.4–5.18.6）

⚠️ 越狱前必做
电量 ≥ 80%
关闭 锁屏密码 / 家长控制
关闭 自动升级 （设置 → 设备选项 → 高级选项 → 无线自动更新 → 关）
备份书籍（越狱不删书，但保险）
准备 电脑 + 原装 USB 线

一、越狱（Nosebleed）
1. 下载文件
下载： nosebleed.zip （书伴 /kindlemodding.org）
解压得到 3 个文件：
jb
jb.sh
patchedUks.sqsh
2. 传文件
Kindle 开 飞行模式
连电脑 → 出现 Kindle 盘
把 3 个文件 放到 根目录 （和 documents 同级）
安全弹出

3. 触发越狱
回到 Kindle → 菜单 → 打开 浏览器
地址栏输入：
plaintext
https://kindlemodding.org/nosb
点页面里的 Jeff Bezos 头像 （点一次）
kindle1

等待 10–30 秒 → 自动回到桌面
出现 “Success!” 或 KUAL 图标 → 越狱成功

4. 安装热修复（防失效）
下载：update_hotfix_universal.bin
放根目录 → 弹出
Kindle：设置 → 菜单 → 更新您的 Kindle

出现错误，再试一次

4. 等待重启 → 完成


二、安装 KUAL + MRPI（必备）
下载：KUAL.zip + MRPI.zip
解压 → 把 extensions 文件夹合并到 Kindle 根目录
弹出 → 桌面出现 KUAL
三、安装 KOReader（HF 版）
你的固件 ≥5.16.3，必须用 HF（hard float）版

下载： KOReader-HF （kindlemodding 或书伴）
解压 → 得到：
extensions
koreader
两个文件夹 直接拷到 Kindle 根目录 （合并覆盖）
弹出

四、使用
打开 KUAL
找到 KOReader → Start KOReader
进入后找 Documents 看书
✅ 完成
原生系统不变
可随时切回 Kindle
支持：EPUB、PDF 重排、裁边、夜间模式、自定义字体
要不要我把 Nosebleed 越狱包、KUAL、MRPI、KOReader-HF 整理成一个下载清单（含地址），你直接下就行？

