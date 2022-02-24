# VSCode 的构造及部件说明

VSCode 的构造说明，帮助了解编辑器的构造及各种部件，这些组成部分都是可以自主拓展或者调用的。了解本文可以更清晰的认知到在开发拓展程序的时候，我们可以做些什么。

<br>

> [官网文档](https://code.visualstudio.com/api/references/extension-guidelines)

## VSCode 的构造

VS Code UI 有两种类型的元素：**Container** 和 **Item**。

<br>

**Container** 是指较外层的主要视图，包括：

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/architecture-groups.png)

<br>

1. Activity Bar
2. Sidebar
3. Editor
4. Panel
5. Status Bar

<br>

**Item** 置于各种各样的 **Containers**，包括：

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/architecture-sections.png)

<br>

6. View Container
7. View
8. View Toolbar
9. Sidebar Toolbar
10. Editor Toolbar
11. View Container
12. Panel Toolbar
13. View
14. Status Bar Item

## Notifications 通知

[Notifications](https://code.visualstudio.com/api/extension-capabilities/common-capabilities#display-notifications) 显示从 VS Code 右下角出现的简要信息。您可以发送三种类型的通知：

- [Information](https://code.visualstudio.com/api/references/vscode-api#window.showInformationMessage)
- [Warning](https://code.visualstudio.com/api/references/vscode-api#window.showWarningMessage)
- [Error](https://code.visualstudio.com/api/references/vscode-api#window.showErrorMessage)

为了减少对用户的骚扰，在你决定使用同之前请参考以下 **通知决策树**：

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/notification-decision-tree.png)

## Views

[Views](https://code.visualstudio.com/api/references/contribution-points#contributes.views) 是可以出现在 sidebar 或 panel 中的容器。Views 可以包含 [tree views](https://code.visualstudio.com/api/extension-guides/tree-view) 或自定义视图，也可以显示视 view actions。用户还可以将视图重新排列到其他 View、Activity Bar item 和 panels 中。限制创建的 Views 数量，因为其他扩展可以在同一视图中做出贡献。

<br>

✔️ should do：
- 尽可能使用现有图标
- 对语言文件使用文件图标
- 使用 [tree views](https://code.visualstudio.com/api/extension-guides/tree-view) 显示数据
- 为每个 Views 添加一个 Activity Bar icon
- 将视图数量保持在最低限度
- 尽量减少名称的长度
- 限制使用自定义 [webview](https://code.visualstudio.com/api/extension-guides/webview)

<br>

❌ not to do：
- 重复现有功能
- 将 tree items 用作单个操作项（例如，搜索栏）
- 如果没有必要，使用自定义 webview 视图
- 使用 view container 在编辑器中启动 webview

#### View locations

视图可以放置在 [已存在的 view containers](https://code.visualstudio.com/api/references/contribution-points#contributes.views) 中，例如文件资源管理器和源代码管理 (SCM) 以及调试视图容器。此外，可以将视图添加到面板中的任何 view container 或它们自己的 自定义 view container 中。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/views-locations.png)

#### View Containers

[View Containers](https://code.visualstudio.com/api/references/contribution-points#contributes.viewsContainers) 是 Activity Bar 的一部分。每个容器都有一个独特的图标，与图标（轮廓）样式的其余部分相匹配。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/view-container.png)

#### Views with progress

如果您的视图位于 SCM 视图容器内，您还可以[在源代码控制视图中显示进度](https://code.visualstudio.com/api/references/vscode-api#ProgressLocation)。

#### Welcome views

当视图为空时，您可以[添加内容来指导用户](https://code.visualstudio.com/api/references/contribution-points#contributes.viewsWelcome)如何使用您的扩展程序或开始使用。欢迎视图中支持链接和图标。

<br>

✔️ should do：
- 尽可能使用链接而不是按钮
- 仅将按钮用于主要操作
- 使用清晰的链接文本来指示链接目标
- 限制内容的长度
- 限制欢迎视图的数量
- 限制视图中的按钮数量

<br>

❌ not to do：
- 使用不必要的按钮
- 使用欢迎视图进行促销
- 使用通用的 “阅读更多” 作为链接文本

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/welcome-views.png)

## Webviews

如果您需要显示超出 VS Code API 支持的自定义功能，您可以使用完全可自定义的 [webviews](https://code.visualstudio.com/api/extension-guides/webview)。重要的是要了解，并且只有在绝对需要时才应使用 [webviews](https://code.visualstudio.com/api/extension-guides/webview)。

<br>

✔️ should do：
- 仅在绝对必要时使用 webviews
- 仅在恰当的上下文环境激活您的 webviews
- 仅在活动窗口打开 webviews
- 确保视图中的所有元素都是可主题化的（请参阅 [webview-view-sample](https://github.com/microsoft/vscode-extension-samples/blob/main/webview-view-sample/media/main.css) 和 [color tokens](https://code.visualstudio.com/api/references/theme-color) 文档）
- 确保您的视图遵循 [无障碍指南](https://code.visualstudio.com/docs/editor/accessibility)（颜色对比、ARIA 标签、键盘导航）
- 在工具栏和视图中使用命令操作

<br>

❌ not to do：
- 用于促销（升级、赞助商等）
- 用于向导
- 在每一扇窗户上打开
- 打开扩展更新（改为通过通知询问）
- 添加与编辑器或工作区无关的功能
- 重复现有功能（欢迎页面、设置、配置等）

#### Webview views

您还可以将 webviews 放入任何视图容器（侧边栏或面板）中，这些元素称为 [webview views](https://code.visualstudio.com/api/references/vscode-api#WebviewView)。相同的 webview 指南适用于 webview 视图。

## Status Bar

[Status Bar](https://code.visualstudio.com/api/extension-capabilities/extending-workbench#status-bar-item) 位于 VS Code 工作台的底部，显示与您的工作区相关的信息和操作，内容分为两组：主要（左）和次要（右）。与整个工作区相关的项目（状态、问题/警告、同步）位于左侧，次要或上下文项目（语言、间距、反馈）位于右侧。限制添加的项目数量，因为其他扩展对同一区域也有使用。

<br>

✔️ should do：
- 使用短文本标签
- 仅在必要时使用图标
- 仅将图标用于清晰的隐喻
- 将主要（全局）项目放在左侧
- 将次要（上下文）项目放在右侧

<br>

❌ not to do：
- 添加自定义颜色
- 添加多个图标（除非必要）
- 添加多个项目（除非必要）

#### Progress Status Bar item
当需要显示谨慎的进度（进度发生在后台）时，建议显示带有加载图标的状态栏项目（您也可以添加旋转动画）。但如果需要提升进度以引起用户注意，我们建议转到进度通知。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/status-bar-progress.png)

#### Error Status Bar item
如果您需要出于错误目的显示高度可见的项目，您可以使用错误状态栏项目。仅将错误状态栏项目用作最后的手段，并且仅用于特殊情况。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/status-bar-error.png)

## Quick Picks

[Quick Picks](https://code.visualstudio.com/api/extension-capabilities/common-capabilities#quick-pick) 是一种执行操作和接收用户输入的简单方法。这在选择配置选项、需要过滤内容或从项目列表中选择时很有帮助。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/quickpick.png)

<br>

✔️ should do：
- 使用图标进行清晰的隐喻
- 使用描述来显示当前项目（如果适用）
- 用详细信息提供（简要）附加上下文
- 对一系列输入使用多步模式（如向导）
- 从列表中挑选时提供创建新项目的选项（如果适用）

<br>

❌ not to do：
- 重复现有功能
- 对多个项目使用相同的图标
- 在列表中使用六个以上的图标

## Editor Actions

[Editor Actions](https://code.visualstudio.com/api/references/contribution-points#contributes.commands) 可以出现在编辑器工具栏中。您可以添加图标作为快速操作，也可以在溢出菜单 (...) 下添加菜单项。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/editor-actions.png)

<br>

✔️ should do：
- 仅在上下文适当时显示
- 使用图标库中的图标
- 使用溢出菜单进行辅助操作

<br>

❌ not to do：
- 添加多个图标
- 添加自定义颜色
- 使用表情符号

## Context Menus

[Menu items](https://code.visualstudio.com/api/references/contribution-points#contributes.menus)出现在视图、操作和右键单击菜单中。菜单分组保持一致很重要。如果您的扩展程序具有与文件相关的操作，请将您的操作放在文件资源管理器上下文菜单中（适当时）。如果扩展程序对某些文件类型具有操作，则仅针对这些项目显示它。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/context-menu.png)

<br>

✔️ should do：
- 在上下文适当时显示操作
- 将类似的操作组合在一起
- 将大组操作放入子菜单

<br>

❌ not to do：
- 在不恰当的上下文中显示每个项操作

## Settings

[Settings](https://code.visualstudio.com/api/references/contribution-points#contributes.configuration) 是用户如何配置您的扩展程序。设置可以是输入框、布尔值、下拉列表、列表、键/值对。如果您的扩展程序需要用户配置特定设置，您可以打开设置界面并通过设置 ID 查询您的扩展程序设置。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/settings.png)

<br>

✔️ should do：
- 为每个设置添加默认值
- 为每个设置添加清晰的描述
- 链接到复杂设置的文档
- 链接到相关的其他设置
- 需要用户配置特定设置时链接到对应的设置 ID

<br>

❌ not to do：
- 创建您自己的设置页面/webview
- 创建长描述

## Command Palette

[Command Palette](https://code.visualstudio.com/api/references/contribution-points#contributes.commands) 是找到所有命令的地方。对您的命令名称进行适当标记非常重要，以便用户可以轻松找到它们。

<br>

![image](https://code.visualstudio.com/assets/api/references/guidelines/command-palette.png)

<br>

✔️ should do：
- 在适当的地方添加键盘快捷键
- 为命令使用清晰的名称
- 将命令组合在同一类别中

<br>

❌ not to do：
- 覆盖现有的键盘快捷键
- 在命令名称中使用表情符号

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。
