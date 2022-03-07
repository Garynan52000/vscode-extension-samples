# VSCode when 子句上下文

Visual Studio Code 根据 VS Code UI 中可见和活动的元素设置各种上下文键和特定值。这些上下文可用于选择性地启用或禁用扩展命令和 UI 元素，例如菜单和视图。

<br>

例如，VS Code 使用 when 子句来启用或禁用命令键绑定，您可以在 Default Keybindings JSON (**Preferences: Open Default Keyboard Shortcuts (JSON)**) 中看到：

<br>

```
{ "key": "f5", "command": "workbench.action.debug.start", "when": "debuggersAvailable && !inDebugMode" },
```

<br>

内置的 **Start Debugging** 命令上方有键盘快捷键 **F5**，该快捷键仅在有适当的调试器可用（context `debuggersAvailable` 为 `true`）且编辑器未处于调试模式（context `inDebugMode` 为 `false`）时启用。

<br>

> [官网文档](https://code.visualstudio.com/api/references/when-clause-contexts)

## 条件运算符

<table>
    <tr>
        <th>Operator</th><th>Symbol</th><th>Example</th>
    </tr>
    <tr>
        <td>等于</td><td><code>==</code></td><td><code>"editorLangId == typescript"</code></td>
    </tr>
    <tr>
        <td>不等于</td><td><code>!=</code></td><td><code>"resourceExtname != .js"</code></td>
    </tr>
    <tr>
        <td>逻辑或</td><td><code>||</code></td><td><code>"isLinux || isWindows"</code></td>
    </tr>
    <tr>
        <td>逻辑与</td><td><code>&&</code></td><td><code>"textInputFocus && !editorReadonly"</code></td>
    </tr>
    <tr>
        <td>非</td><td><code>!</code></td><td><code>"!editorReadonly"</code></td>
    </tr>
    <tr>
        <td>Matches 正则匹配</td><td><code>!</code></td><td><code>"resourceScheme =~ /^untitled$|^file$/"</code></td>
    </tr>
    <tr>
        <td>大于、大于等于</td><td><code>&gt; &gt;=</code></td><td><code>"gitOpenRepositoryCount &gt;= 1"</code></td>
    </tr>
    <tr>
        <td>小于、小于等于</td><td><code>&lt; &lt;=</code></td><td><code>"workspaceFolderCount &lt;= 2"</code></td>
    </tr>
    <tr>
        <td>In</td><td><code>in</code></td><td><code>"resourceFilename in supportedFolders"</code><a href="https://code.visualstudio.com/api/references/when-clause-contexts#in-conditional-operator" target="_blank">详情如下</a></td>
    </tr>
</table>

## key-value 的 when 子句运算符

when 子句有一个键值对匹配运算符。表达式 `key =~ value` 将右侧视为正则表达式以匹配左侧。例如，要为所有 Docker 文件提供上下文菜单项，可以使用：

<br>

```
"when": "resourceFilename =~ /docker/"
```

<br>

[此处的列表](https://code.visualstudio.com/api/references/when-clause-contexts#available-contexts)并不详尽，您可以通过在键盘快捷键编辑器中搜索和过滤找到其他 `when` 子句上下文（**Preferences: Open Keyboard Shortcuts**）或查看默认键绑定 JSON 文件（**Preferences: Open Default Keyboard Shortcuts (JSON)**）。

<table>
    <tr>
        <th>Context name</th><th>True when</th>
    </tr>
    <tr>
        <td colspan="2">编辑器相关</td>
    </tr>
    <tr>
        <td><code>editorFocus</code></td><td>编辑器具有焦点，文本或小部件。</td>
    </tr>
    <tr>
        <td><code>editorTextFocus</code></td><td>编辑器中的文本具有焦点（光标闪烁）。</td>
    </tr>
    <tr>
        <td><code>textInputFocus</code></td><td>任何编辑器有焦点（常规编辑器、调试 REPL 等）。</td>
    </tr>
    <tr>
        <td><code>inputFocus</code></td><td>任何文本输入区域有焦点（编辑器或文本框）。</td>
    </tr>
    <tr>
        <td><code>editorHasSelection</code></td><td>在编辑器中选择文本。</td>
    </tr>
    <tr>
        <td><code>editorHasMultipleSelections</code></td><td>选择了多个文本区域（多个光标）。</td>
    </tr>
    <tr>
        <td><code>editorReadonly</code></td><td>编辑器是只读的。</td>
    </tr>
    <tr>
        <td><code>editorLangId</code></td><td>当编辑器的关联 <a href="https://code.visualstudio.com/docs/languages/identifiers" target="_blank">language ID</a> 匹配时为真。示例：<code>"editorLangId == typescript"</code>。</td>
    </tr>
    <tr>
        <td><code>isInDiffEditor</code></td><td>活动编辑器是差异编辑器。</td>
    </tr>
    <tr>
        <td><code>isInEmbeddedEditor</code></td><td>当焦点位于嵌入式编辑器内时为真。</td>
    </tr>
    <tr>
        <td colspan="2">操作系统相关</td>
    </tr>
    <tr>
        <td><code>isLinux</code></td><td>操作系统是 Linux</td>
    </tr>
    <tr>
        <td><code>isMac</code></td><td>操作系统是 Mac</td>
    </tr>
    <tr>
        <td><code>isWindows</code></td><td>操作系统是 Windows</td>
    </tr>
    <tr>
        <td><code>isWeb</code></td><td>从 Web 访问编辑器</td>
    </tr>
    <tr>
        <td colspan="2">模式上下文</td>
    </tr>
    <tr>
        <td><code>inSnippetMode</code></td><td>编辑器处于片段模式。</td>
    </tr>
    <tr>
        <td><code>inQuickOpen</code></td><td>快速打开下拉菜单具有焦点。</td>
    </tr>
    <tr>
        <td colspan="2">资源上下文</td>
    </tr>
    <tr>
        <td><code>resourceScheme</code></td><td>当资源 Uri scheme 匹配时为真。示例：<code>"resourceScheme == file"</code></td>
    </tr>
    <tr>
        <td><code>resourceFilename</code></td><td>当资源管理器或编辑器文件名匹配时为真。例子：<code>"resourceFilename == gulpfile.js"</code></td>
    </tr>
    <tr>
        <td><code>resourceExtname</code></td><td>当资源管理器或编辑器文件扩展名匹配时为真。例子：<code>"resourceExtname == .js"</code></td>
    </tr>
    <tr>
        <td><code>resourceDirname</code></td><td>当资源管理器或编辑器的资源绝对文件夹路径匹配时为真。例子：<code>"resourcePath == /users/alice/project/gulpfile.js"</code></td>
    </tr>
    <tr>
        <td><code>resourceLangId</code></td><td>当资源管理器或编辑器标题 <a href="">language ID</a> 匹配时为真。例子：<code>"resourceLangId == markdown"</code></td>
    </tr>
    <tr>
        <td><code>resourceLangId</code></td><td>当资源管理器或编辑器标题 <a href="">language ID</a> 匹配时为真。例子：<code>"resourceLangId == markdown"</code></td>
    </tr>
    <tr>
        <td><code>isFileSystemResource</code></td><td>当资源管理器或编辑器文件是可以从文件系统提供程序处理的文件系统资源时为真</td>
    </tr>
    <tr>
        <td><code>resourceSet</code></td><td>设置资源管理器或编辑器文件时为真</td>
    </tr>
    <tr>
        <td><code>resource</code></td><td>Explorer 或编辑器文件的完整 Uri</td>
    </tr>
    <tr>
        <td colspan="2">资源管理器上下文</td>
    </tr>
    <tr>
        <td><code>explorerViewletVisible</code></td><td>如果资源管理器视图可见，则为真。</td>
        <td><code>explorerViewletFocus</code></td><td>如果资源管理器视图具有键盘焦点，则为真。</td>
        <td><code>filesExplorerFocus</code></td><td>如果文件资源管理器部分具有键盘焦点，则为真。</td>
        <td><code>openEditorsFocus</code></td><td>如果 OPEN EDITORS 部分具有键盘焦点，则为真。</td>
        <td><code>explorerResourceIsFolder</code></td><td>如果在资源管理器中选择了文件夹，则为真。</td>
    </tr>
    <tr>
        <td colspan="2">编辑器小部件上下文</td>
    </tr>
    <tr>
        <td><code>findWidgetVisible</code></td><td>编辑器查找小部件可见。</td>
        <td><code>suggestWidgetVisible</code></td><td>建议小部件 (IntelliSense) 可见。</td>
        <td><code>suggestWidgetMultipleSuggestions</code></td><td>显示多个建议。</td>
        <td><code>renameInputVisible</code></td><td>重命名输入文本框可见。</td>
        <td><code>referenceSearchVisible</code></td><td>Peek References 预览窗口打开。</td>
        <td><code>inReferenceSearchEditor</code></td><td>Peek References peek 窗口编辑器具有焦点。</td>
        <td><code>config.editor.stablePeek</code></td><td>保持 peek 编辑器打开（由 <code>editor.stablePeek</code> 设置控制）。</td>
        <td><code>quickFixWidgetVisible</code></td><td>快速修复小部件可见。</td>
        <td><code>parameterHintsVisible</code></td><td>参数提示是可见的（由 editor.parameterHints.enabled 设置控制）。</td>
        <td><code>parameterHintsMultipleSignatures</code></td><td>显示多个参数提示。</td>
    </tr>
    <tr>
        <td colspan="2">调试器上下文</td>
    </tr>
    <tr>
        <td><code>debuggersAvailable</code></td><td>有适当的调试器扩展可用。</td>
        <td><code>inDebugMode</code></td><td>调试会话正在运行。</td>
        <td><code>debugState</code></td><td>活动调试器状态。可能的值是 <code>inactive</code>, <code>initializing</code>, <code>stopped</code>, <code>running</code>。</td>
        <td><code>debugType</code></td><td>当调试类型匹配时为真。示例：<code>"debugType == 'node'"</code>。</td>
        <td><code>inDebugRepl</code></td><td>焦点在调试控制台 REPL。</td>
    </tr>
    <tr>
        <td colspan="2">集成终端上下文</td>
    </tr>
    <tr>
        <td><code>terminalFocus</code></td><td>集成终端具有焦点。</td>
        <td><code>terminalIsOpen</code></td><td>打开一个集成终端。</td>
    </tr>
    <tr>
        <td colspan="2">时间线视图上下文</td>
    </tr>
    <tr>
        <td><code>timelineFollowActiveEditor</code></td><td>如果时间轴视图跟随活动编辑器，则为真。</td>
    </tr>
    <tr>
        <td colspan="2">时间线视图项目上下文</td>
    </tr>
    <tr>
        <td><code>timelineItem</code></td><td>当时间线项目的上下文值匹配时为真。示例：<code>"timelineItem =~ /git:file:commit\\b/"</code>。</td>
    </tr>
    <tr>
        <td colspan="2">扩展上下文</td>
    </tr>
    <tr>
        <td><code>extension</code></td><td>当扩展程序的 ID 匹配时为真。示例：<code>"extension == eamodio.gitlens"</code>。</td>
    </tr>
    <tr>
        <td><code>extensionStatus</code></td><td>安装扩展时为真。示例：<code>"extensionStatus == installed"</code>。</td>
    </tr>
    <tr>
        <td><code>extensionHasConfiguration</code></td><td>如果扩展有配置，则为真。</td>
    </tr>
    <tr>
        <td colspan="2">全局 UI 上下文</td>
    </tr>
    <tr>
        <td><code>notificationFocus</code></td><td>通知具有键盘焦点。</td>
    </tr>
    <tr>
        <td><code>notificationCenterVisible</code></td><td>通知中心在 VS Code 的右下角可见。</td>
    </tr>
    <tr>
        <td><code>notificationToastsVisible</code></td><td>通知 toast 在 VS Code 的右下角可见。</td>
    </tr>
    <tr>
        <td><code>searchViewletVisible</code></td><td>搜索视图已打开。</td>
    </tr>
    <tr>
        <td><code>sideBarVisible</code></td><td>显示侧边栏。</td>
    </tr>
    <tr>
        <td><code>sideBarFocus</code></td><td>侧边栏有焦点。</td>
    </tr>
    <tr>
        <td><code>panelFocus</code></td><td>Panel 有焦点。</td>
    </tr>
    <tr>
        <td><code>inZenMode</code></td><td>窗口处于 Zen 模式。</td>
    </tr>
    <tr>
        <td><code>isCenteredLayout</code></td><td>编辑器处于居中布局模式。</td>
    </tr>
    <tr>
        <td><code>workbenchState</code></td><td>Can be <code>empty</code>, <code>folder</code> (1 folder), or <code>workspace</code>.</td>
    </tr>
    <tr>
        <td><code>workspaceFolderCount</code></td><td>工作区文件夹的计数。</td>
    </tr>
    <tr>
        <td><code>replaceActive</code></td><td>搜索视图替换文本框打开。</td>
    </tr>
    <tr>
        <td><code>view</code></td><td>当视图标识符匹配时为真。例子： <code>"view == myViewsExplorerID"</code>。</td>
    </tr>
    <tr>
        <td><code>viewItem</code></td><td>当 viewItem 上下文匹配时为真。例子： <code>"viewItem == someContextValue"</code>。</td>
    </tr>
    <tr>
        <td><code>isFullscreen</code></td><td>当窗口全屏时为真。</td>
    </tr>
    <tr>
        <td><code>focusedView</code></td><td>当前焦点视图的标识符。</td>
    </tr>
    <tr>
        <td><code>canNavigateBack</code></td><td>如果可以返回，则为真。</td>
    </tr>
    <tr>
        <td><code>canNavigateForward</code></td><td>如果可以向前导航，则为真。</td>
    </tr>
    <tr>
        <td><code>canNavigateToLastEditLocation</code></td><td>如果可以导航到最后一个编辑位置，则为真。</td>
    </tr>
    <tr>
        <td colspan="2">全局编辑器 UI 上下文</td>
    </tr>
    <tr>
        <td><code>textCompareEditorVisible</code></td><td>至少一个差异（比较）编辑器是可见的。</td>
    </td>
    <tr>
        <td><code>textCompareEditorActive</code></td><td>差异（比较）编辑器处于活动状态。</td>
    </td>
    <tr>
        <td><code>editorIsOpen</code></td><td>如果一个编辑器打开，则为真。</td>
    </td>
    <tr>
        <td><code>groupEditorsCount</code></td><td>辑器分组中的辑器的数量。</td>
    </td>
    <tr>
        <td><code>activeEditorGroupEmpty</code></td><td>如果活动编辑器组没有编辑器，则为真。</td>
    </td>
    <tr>
        <td><code>activeEditorGroupIndex</code></td><td>从 1 开始的数字，反映编辑器组在编辑器网格中的位置。索引为 1 的组将位于左上角的第一个。</td>
    </td>
    <tr>
        <td><code>activeEditorGroupLast</code></td><td>将适用于编辑器网格中的最后一个编辑器组。</td>
    </td>
    <tr>
        <td><code>multipleEditorGroups</code></td><td>当存在多个编辑器组时为真。</td>
    </td>
    <tr>
        <td><code>activeEditor</code></td><td>组中活动编辑器的标识符。</td>
    </td>
    <tr>
        <td><code>activeEditorIsDirty</code></td><td>当组中的活动编辑器脏时为真。</td>
    </td>
    <tr>
        <td><code>activeEditorIsNotPreview</code></td><td>当组中的活动编辑器未处于预览模式时为真。</td>
    </td>
    <tr>
        <td><code>activeEditorIsPinned</code></td><td>当组中的活动编辑器被固定时为真。</td>
    </td>
    <tr>
        <td><code>inSearchEditor</code></td><td>当焦点位于搜索编辑器内时为真。</td>
    </td>
    <tr>
        <td colspan="2">配置设置上下文</td>
    </tr>
    <tr>
        <td><code>config.editor.minimap.enabled</code></td><td>当设置 <code>editor.minimap.enabled</code> 为真时为真。</td>
    </tr>
</table>

> 注意：您可以使用任何用户或工作区设置，在此处计算为布尔值并带有前缀 `"config."`。

## Active/focused 视图或面板的 when 子句上下文

<table>
    <tr>
        <th>Context name</th><th>True when</th>
    </tr>
    <tr>
        <td><code>activeViewlet</code></td><td>当视图可见时为真。例子： <code>"activeViewlet == 'workbench.view.explorer'"</code></td>
    </tr>
    <tr>
        <td><code>activePanel</code></td><td>面板可见时为真。例子： <code>"activePanel == 'workbench.panel.output'"</code></td>
    </tr>
    <tr>
        <td><code>focusedView</code></td><td>当视图聚焦时为真。示例： <code>"focusedView == myViewsExplorerID"</code></td>
    </tr>
</table>

#### View Identifiers:

- workbench.view.explorer - File Explorer
- workbench.view.search - Search
- workbench.view.scm - Source Control
- workbench.view.debug - Run
- workbench.view.extensions - Extensions

#### Panel Identifiers:

- workbench.panel.markers - Problems
- workbench.panel.output - Output
- workbench.panel.repl - Debug Console
- terminal - Integrated Terminal
- workbench.panel.comments - Comments
- workbench.view.search - Search when `search.location` is set to `panel`

如果您想要一个仅在特定视图或面板具有焦点时启用的 when 子句，请将 `sideBarFocus` 或 `panelFocus` 与 `activeViewlet` 或 `activePanel` 结合使用。例如，下面的 when 子句仅在文件资源管理器具有焦点时才为真：

<br>

```
"sideBarFocus && activeViewlet == 'workbench.view.explorer'"
```

## 检查 when 子句中的设置

在 when 子句中，您可以通过在其前面加上 `config.` 来引用配置（设置）值，例如 `config.editor.tabCompletion` 或 `config.breadcrumbs.enabled`。

## 添加自定义 when 子句上下文

如果您正在编写自己的 VS Code 扩展并且需要使用 `when` 子句上下文来启用/禁用命令、菜单或视图，并且现有的键都不适合您的需要，您可以使用 `setContext` 命令添加自己的上下文。

<br>

下面的第一个示例将键 `myExtension.showMyCommand` 设置为 `true`，您可以将其用于启用命令或使用 `when` 属性。第二个示例存储一个值，您可以将其与 `when` 子句一起使用，以检查酷开放事物的数量是否大于 `2`。

<br>

```
vscode.commands.executeCommand('setContext', 'myExtension.showMyCommand', true);

vscode.commands.executeCommand('setContext', 'myExtension.numberOfCoolOpenThings', 4);
```

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。