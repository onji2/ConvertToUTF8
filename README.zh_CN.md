说明
------------------
通过本插件，您可以编辑并保存目前编码不被 Sublime Text 支持的文件，特别是中日韩用户使用的 GB2312，GBK，BIG5，EUC-KR，EUC-JP 等。

![ConvertToUTF8](http://dl.dropbox.com/u/31937639/ConvertToUTF8/ConvertToUTF8.gif)

我现在正努力让 ConvertToUTF8 同时支持 Sublime Text 2 和 3。如果您觉得本插件对您有所帮助，您可以请我喝杯咖啡让我保持清醒。谢！:)

[![通过支付宝请我](http://dl.dropbox.com/u/31937639/alipay.png)](https://me.alipay.com/seanliang)
[![通过PayPal请我](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=GP6Y25N7Q9E26&lc=US&item_name=Buy%20me%20a%20cup%20of%20coffee&item_number=ConvertToUTF8&no_note=0&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donate_LG%2egif%3aNonHostedGuest)

注意
------------------
** Linux 用户：Sublime Text 2 和 3 内嵌 Python 版本中缺失几个 ConvertToUTF8 依赖的动态库。您必须手工安装这些文件才能让本插件完全运作。

** OS X 用户：Sublime Text 3 使用的内嵌 Python 存在与 Linux 版本相同的问题。

** 我已将此问题报告给 Jon 但未收到任何回复，因此我将创建额外的插件来解决它。如果您急于在发布之前使用本插件，请与我联系获取更多信息。

安装
------------------
推荐使用 [Package Control](http://wbond.net/sublime_packages/package_control) 查找 *ConvertToUTF8* 进行自动下载安装与更新。

如需手工安装，请将本项目打包下载并解压，将解压后的文件夹名修改为 *ConvertToUTF8* ，然后将此文件夹移动到 Sublime Text 的 *Packages* 文件夹下（可通过 Sublime Text 菜单中的 Preferences > Browse Packages 找到 *Packages* 文件夹）。

您的文件夹应该看起来是这样的：

![Folder Hierarchy](http://dl.dropbox.com/u/31937639/ConvertToUTF8/hierarchy.png)

设置
------------------
请查看 ConvertToUTF8.sublime-settings 文件获取详细信息。为防止更新插件时被覆盖，请将个人设置保存到 User 目录中名为 ConvertToUTF8.sublime-settings 文件中。

* encoding_list：检测失败时显示的编码列表
* max_cache_size：最大编码缓存数量，0 表示不缓存（默认为 100）
* max_detect_lines：最大检测行数，0 表示不限制（默认为 600）
* preview_action：指定预览模式下的动作，可选项：no_action 不作任何动作，convert_and_open 转换编码并打开（默认为 no_action）
* default_encoding_on_create：指定新建文件的默认编码（如 GBK），空值表示使用 Sublime Text 的 default_encoding 设置（默认为空值）
* convert_on_load：启用/禁用文件装载时将窗口内容转换成UTF-8编码，可选项：always 自动转换，never 不转换（默认为 always）
* convert_on_save：启用/禁用文件保存时将其从UTF-8转换成指定转码，可选项：always 自动转换，never 不转换（默认为 always）

使用说明
------------------
多数情况下，本插件将自动对处理编码相关的事项。

您也可以通过 File > Set File Encoding to 菜单对文件编码进行手工转换。例如，您可以打开一个 UTF-8 编码的文件，指定保存为 GBK，反之亦然。

注意：
* 如果 convert_on_save 被设置为 never，文件不会被保存成指定编码
* 在文件编码检测过程完成前请勿编辑文件
* 若检测结果不准确，请尝试增大 max_detect_lines 的值或手工指定编码


常见问题
------------------
* 问：安装后无法工作，要如何修复？

  答：请尝试以下步骤：
  1. 重启 Sublime Text
  2. 请确认插件目录名为 ConvertToUTF8（如果是通过 Package Control 安装的可略过此步骤）
  3. 参见[上述“注意”条目](#注意)
  4. 禁用其他编码相关的插件
  5. 联系我

* 问：这个插件支持哪些编码？

  答：只要您的系统支持的编码应该都可使用。

* 问：为何有时重新激活窗口，里面的内容会变乱码？

  答：此问题是由重新载入引起的，且已修复，请更新 *ConvertToUTF8* 插件到最新版本。

* 问：为什么重新激活窗口时，ST2 问我文件“已经被修改。是否要重新载入？”

  答：原因与上一条相同。如果您有未保存的修改，请选择“取消”。

* 问：在保存文件时，Sublime Text 为什么提示将文件保存为 UTF-8？

  答：没有关系，本插件会自动将文件内容保存为原始编码。

* 问：我的文件被保存为UTF-8，而且变成了乱码，要如何恢复？

  答：请打开这个文件，并确认它的编码是UTF-8，然后选择菜单项目“File -> Save with Encoding -> Western (Windows 1252)”，关闭再重新打开该文件即可。

联系我
------------------
请发送您的问题或建议给我：sunlxy (at) yahoo.com 或 http://weibo.com/seanliang
