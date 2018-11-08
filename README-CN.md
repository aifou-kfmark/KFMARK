# 快否 来自爱否科技

![KFMARK logo](https://user-images.githubusercontent.com/5908006/47543804-847b9680-d916-11e8-9861-c0c7b2d39c56.png)

请注意，本程序仍处在早期开发阶段。虽然我们打算将其打造成一款免费软件，但快否仍然是一个商业项目，因此目前无开源计划。北京爱否科技有限公司保留所有权利，禁止一切未经许可的修改、发布以及逆向工程。

## 安装及运行

请在 [Release page](https://github.com/Septillion/KFMARK/releases) 下载以下两个文件：

- KFMARK Beta Android APK
- KFMARK PC Assistant

在手机上安装 APK 之后，你需要在设置中启用 `开发者模式`，并开启 `USB调试`（请自行搜索对应机型的启用方法）。之后打开 KFMARK PC Assistant，连接手机以激活快否的后台`daemon`，之后可以断开与电脑的连接。每次重启手机之后，都需要重新激活。

对于 Mac 和 Linux 用户，请下载 `KFMARK Beta APK` 和 `daemon` 文件，随后从 [Android 开发者官网](https://developer.android.com/studio/releases/platform-tools) 下载 `adb`，并将 `daemon` 放到 `adb` 所在目录。在手机上安装 APK 之后，你需要在设置中启用 `开发者模式`，并开启 `USB调试`（请自行搜索对应机型的启用方法）。之后在电脑的 `终端` 上导航到 `adb` 所在目录，运行以下命令：

	./adb push daemon /data/local/tmp
	./adb shell chmod 777 /data/local/tmp/daemon
	./adb shell "./data/local/tmp/daemon &"

## 功能

快否可以实时显示 Android 游戏运行时的帧率（FPS），来直观展示游戏的流畅度。你也可以选择记录游戏运行过程中的帧率波动曲线、CPU 频率和电量下降情况。记录历史保存在手机本地，以供随时查看。

快否兼容 Android 5.0 及以上系统。

## 隐私

快否在手机本地运行，所需权限仅有「储存」一项。所有的测试历史都保存在手机本地，不会上传到任何服务器上。在程序启动时，快否将会获取手机的型号，并与「手机评分」微信小程序的数据库进行比对，以获取硬件信息（SoC 型号、GPU 型号和屏幕分辨率）。我们不会记录这项请求，因此不会用于识别你的身份。

## 已知问题

### 手机断开链接之后，立刻回到未激活的状态

在某些厂商（如 OPPO）的设备上，一旦手机断开与 PC 的连接，将会立刻终止所有后台调试程序。快否依赖后台 `daemon` 来运行，因此在这些手机上，请在测试全程保持与 PC 的连接。已知机型：

- OPPO 所有机型
- 华为 Mate 20

### 《堡垒之夜》提示“无法在 USB 调试模式下进行游戏”

一些游戏外挂（例如触摸映射、自动压枪）等，需要“USB 调试”来运行。《堡垒之夜》（Fortnite）为了防止后台外挂，禁止在“USB 调试模式”下进行游戏。然而快否也需要通过“USB 调试”模式来在后台运行一个辅助程序，用于检测帧率，因此无法运行《堡垒之夜》。目前在 Android 端没有办法可以测试正常渠道发行的《堡垒之夜》。我们不推荐用户对游戏进行进一步修改，以防止封号。

### PC 助手一直提示未连接手机

因为 adb 命令的限制，PC 助手必须放在纯英文路径下才可以正常运行。将 PC 助手的文件夹放在 C 盘根目录，再运行激活即可。

## 错误报告

请访问 [Issues page](https://github.com/Septillion/KFMARK/issues) 提交错误报告。提交前请务必搜索是否有人提交过重复 Bug。

提交 Bug 时，请遵循如下格式：

	Device Model:
	Device Android Version:
	Device ROM Version:
	---
	Bug Description:
	---
	Steps to Reproduce:
