# 复刻说明：本人仅提供汉化，所有链接均跳转至原作者项目

复刻自 [Petschko/Java-RPG-Maker-MV-Decrypter](https://github.com/Petschko/Java-RPG-Maker-MV-Decrypter)

[下载汉化版本](https://github.com/dumplingcoke/Java-RPG-Maker-MV-Decrypter/releases)

----

# 重要：项目已迁移至 [Gitlab.com](https://gitlab.com/Petschko/Java-RPG-Maker-MV-Decrypter)

请前往该地址查看更新/提交错误报告 - 原作者的Github仓库已转为只读模式

https://gitlab.com/Petschko/Java-RPG-Maker-MV-Decrypter

----

# Petschko的RPG-Maker-MV/MZ文件解密工具（Java版）

## 这是什么？
本项目用于解密RPG-Maker-MV/MZ通过内置加密功能加密的资源文件。

该项目还能解密整个RPG项目目录。它与[作者之前的项目](https://gitlab.com/Petschko/RPG-Maker-MV-Decrypter)类似，但使用更加便捷。

### 该程序能解密哪些文件？
可以解密RPG Maker MV或MZ内置加密的文件。这些文件通常具有以下扩展名：`.rpgmvp`、`.rpgmvm`、`.rpgmvo`、`.png_`、`.m4a_` 或 `.ogg_`。

## 运行要求
- Java 8或更高版本
- 支持任何操作系统（Linux、Windows、IOS等）

## 安装
- [下载ZIP包（!原作者的!!!Alpha版!!）- 版本：0.4.2](https://petschko.org/upload/projects/java-rpg-maker-decrypter/RPG_Maker_MV_Decrypter_jar_0.4.2.zip) 或克隆/下载项目后自行构建JAR文件
- 将文件放置于任意位置（如果下载的是ZIP包，别忘了解压）

### 依赖项（仅自行构建JAR时需要）
- [org.json](https://github.com/douglascrockford/JSON-java)

## 使用方法
### （常规）图形界面操作
- 双击JAR文件即可启动程序 *（若无法启动可尝试下载原作者的英文版，并且使用start.bat文件进行启动 - 仅限Windows）*
- 点击菜单栏"文件"中的"选择RPG MV/MZ项目..."
  - 浏览至需要解密的RPG-Maker MV项目目录
  - 选择项目主目录（包含Game.exe的文件夹）后点击右下角的"打开"
    - 也可以将程序直接放在游戏目录内，然后选择"从当前目录中选择项目"选项
- 稍等片刻 =)
- 如果文件列表已显示且解密密钥已填入文本框，即可开始解密
  - 点击菜单栏"解密" -> "全部文件"
  - 稍等片刻即可完成 =)
  - 解密后的文件将保存在程序所在目录的"Output"文件夹中 *（如果你没有通过"文件" -> "更改输出目录..."修改输出路径的话）*

- （尚未实现）也可以解密单个/多个文件 - 在"Project-Files"标签页选中文件后，点击"Decrypter" -> "Selected Files"
- 还可以重新加密文件（例如为游戏翻译图片文字后）
- 可以通过"选项"菜单检查设置是否符合需求 =)
- （尚未实现）"信息"菜单中也可查看本"使用说明"

### 命令行运行 - 适用于自动化操作/命令行爱好者 :3

某些情况下使用命令行更为便捷。例如想要制作游戏模组时，可以让用户只需运行.bat/.sh文件即可完成操作。

- 查看全局帮助（包含所有子命令）：`java -jar "RPG Maker MV Decrypter.jar" help`
- 查看特定命令的详细帮助：`java -jar "RPG Maker MV Decrypter.jar" [command] help`
  - 示例（显示解密帮助）：`java -jar "RPG Maker MV Decrypter.jar" decrypt help`

详细使用方法和示例请参阅[命令行指令说明](cmd-instructions.md)

## 开发动机
作为RPG-Maker的内容创作者，有时很难确认他人是否在使用你的资源 *（例如未署名或违规将非商用资源用于商业游戏等）*。

我没有时间玩遍所有游戏（虽然很想^^），所以只是快速查看文件，但前提是文件未被加密...

遗憾的是，越来越多人使用RPG-Maker-MV的内置加密功能，因此我开发了这个程序 - 无需通关即可快速查看文件 =) 希望其他创作者也能觉得这个工具实用。

对翻译者也很有用，例如想让游戏支持多语言时。*（我认为应该先获得游戏作者的许可！- 虽然有时无法实现...）*

我个人对加密技术也很感兴趣，由于MV的加密较为简单，这是很好的学习案例 - 但正因其简单，才不会拖慢低配设备的运行速度！*（见下文）*

### 为什么我的游戏加密在此情况下无效？
有时看到喜欢的图片想保存，即使没有这个解密器，你也可以通过截图（或录音）实现 >.<

由此可见RPG-Maker游戏其实不需要加密...如果有人想要获取文件，总会有办法，这在3A游戏中也屡见不鲜。
你无法100%加密文件，因为游戏本身需要解密才能显示...（或播放） - 既然游戏支持离线运行，就意味着必须提供解密方法和密钥。

### 但有人会盗用我的素材
确实可能发生，但如前所述，无论如何都无法完全阻止（即使没有这个解密器）。即使使用更强大的加密，也只会拖慢低配设备上的游戏运行速度。
任何人都可以保存内容仅供**个人使用**！但**不允许**用其制作游戏。除非是免费资源，但必须遵守资源创作者的授权条款！
所以请勿盗用素材，同为创作者，我深知制作这些内容需要投入的时间，请尊重他人的劳动成果！

### 为什么选择Java开发？| 优势
这个Java解密器更适合处理整个目录或自动化脚本。使用Java开发更便捷，因为JavaScript在文件访问/保存等方面限制较多。
为什么是Java？- 因为我熟悉这个语言 xP - 欢迎移植到其他不需要运行环境的语言...

**相比我之前项目的优势：**
- 支持整个目录操作
  - 自动检测加密文件
  - 自动保存并重命名解密文件！
  - 保持目录结构
  - 可指定输出目录
- 能自动检测加密文件和密钥
- 比JavaScript版更稳定快速，不受浏览器和字符集问题影响...
- 支持命令行操作
  - 或许可用于模组制作？听说有人这么做
- 未来将添加项目恢复功能
- 可启用/禁用16字节伪头部验证
  - 禁用验证时，仅移除文件前16字节的伪头部 *（当解密器签名变更时很有用）*
  - 启用验证时会检查文件头部是否正确（即是否为真正的加密文件）

## 请遵守规则！
**如果原始资源授权不允许**，你**无权使用**解密后的文件。
请**勿公开盗用、二次使用或分享**！这不是本程序的初衷！

解密文件**仅限个人使用**。如果原始授权允许，当然可以使用，但请遵守授权条款！

**如果是你自己的项目**，只是丢失了原始文件，**你享有与之前相同的权利**处理这些文件 =)

## 捐赠

如果喜欢这个项目并想表示感谢，可以考虑[捐赠](https://www.paypal.me/petschko)。我更看重能帮助项目发展的贡献（Pull请求、错误报告等），这些比捐赠更有价值，但同样感谢任何形式的支持 ^.^

## 联系方式
- 如有疑问可邮件联系（请不要发送错误报告）：peter@petschko.org
  - 也可以告诉我你是否喜欢这个项目 >.< 当然也欢迎提出改进建议
- 错误报告请使用gitlab.com上的"[Issue](https://gitlab.com/Petschko/Java-RPG-Maker-MV-Decrypter/-/issues)"功能
