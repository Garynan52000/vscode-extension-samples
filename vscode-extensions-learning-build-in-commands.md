# VSCode 内置命令

本文档列出了可与 `vscode.commands.executeCommand` API 一起使用的 Visual Studio Code 命令的子集。

<br> 

阅读[命令指南](https://code.visualstudio.com/api/extension-guides/command)以了解如何使用命令 API。

<br>

以下是如何在 VS Code 中打开新文件夹的示例：

<br>

```
let uri = Uri.file('/some/path/to/folder');
let success = await commands.executeCommand('vscode.openFolder', uri);
```

<br>

> [官网文档](https://code.visualstudio.com/api/references/commands)

## 命令

#### `vscode.executeDocumentHighlights` 执行文档突出显示提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - DocumentHighlight 实例数组的 Promise。

#### `vscode.executeDocumentSymbolProvider` 执行文档 Symbol 提供程序

- uri - 文本文档的 Uri
- (returns) - SymbolInformation 和 DocumentSymbol 实例数组的 Promise。

#### `vscode.executeFormatDocumentProvider` 执行文档格式提供程序

- uri - 文本文档的 Uri
- options - Formatting options
- (returns) - 一组 TextEdits 的 Promise。

#### `vscode.executeFormatRangeProvider` 执行范围格式提供程序

- uri - 文本文档的 Uri
- range - 文本文档中的范围
- options - Formatting options
- (returns) - 一组 TextEdits 的 Promise。

#### `vscode.executeFormatOnTypeProvider` 在类型提供程序上执行格式

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- ch - Trigger character
- options - Formatting options
- (returns) - 一组 TextEdits 的 Promise。

#### `vscode.executeDefinitionProvider` 执行所有定义提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 一组 Location 或 LocationLink 实例的 Promise。

#### `vscode.executeDeclarationProvider` 执行所有声明提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 一组 Location 或 LocationLink 实例的 Promise。

#### `vscode.executeImplementationProvider` 执行所有实现提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 一组 Location 实例的 Promise。

#### `vscode.executeReferenceProvider` 执行所有参考提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 一组 Location 或 LocationLink 实例的 Promise。

#### `vscode.executeHoverProvider` 执行所有悬停提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 组 Hover 实例的 Promise。

#### `vscode.executeSelectionRangeProvider` 执行选择范围提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - 范围数组的 Promise。

#### `vscode.executeWorkspaceSymbolProvider` 执行所有工作区 symbol 提供程序

- query - Search string
- (returns) - SymbolInformation-instances 数组的 Promise。

#### `vscode.prepareCallHierarchy` 在文档内的某个位置准备调用层次结构

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- (returns) - CallHierarchyItem 或 undefined

#### `vscode.provideIncomingCalls` 计算项目的呼入调用

- item - A call hierarchy item
- (returns) - CallHierarchyItem 或 undefined

#### `vscode.provideOutgoingCalls` 计算项目的呼出调用

- item - A call hierarchy item
- (returns) - CallHierarchyItem 或 undefined

#### `vscode.executeDocumentRenameProvider` 执行重命名提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- newName - 新的 symbol name
- (returns) - WorkspaceEdit Promise。

#### `vscode.executeLinkProvider` 执行文档链接提供程序

- uri - 文本文档的 Uri
- linkResolveCount - (optional) 应解析的链接数，仅当链接未解析时。
- (returns) - DocumentLink-instances 实例数组的 Promise。

#### `vscode.provideDocumentSemanticTokensLegend` 为文档提供语义标记图例

- uri - 文本文档的 Uri
- (returns) - SemanticTokensLegend Promise。

#### `vscode.provideDocumentSemanticTokens` 为文档提供语义标记

- uri - 文本文档的 Uri
- (returns) - SemanticTokens Promise。

#### `vscode.provideDocumentRangeSemanticTokensLegend` 为文档范围提供语义标记图例

- uri - 文本文档的 Uri
- range - 文本文档中的范围
- (returns) - SemanticTokens Promise。

#### `vscode.executeCompletionItemProvider` 执行完成项提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- triggerCharacter - (optional) 当用户键入字符时触发完成，例如 `,` 或  `(`
- itemResolveCount - (optional) 要解决的完成数（太大的数字会减慢完成速度）
- (returns) - CompletionList-instance Promise。

#### `vscode.executeSignatureHelpProvider` 执行签名帮助提供程序

- uri - 文本文档的 Uri
- position - 文本文档中的位置
- triggerCharacter - (optional) 当用户键入字符时触发完成，例如 `,` 或  `(`
- (returns) - SignatureHelp Promise。

#### `vscode.executeCodeLensProvider` 执行代码镜头提供者

- uri - 文本文档的 Uri
- itemResolveCount - (optional) 镜头应该解决并返回号码。只会返回已解决的镜头，会影响性能）
- (returns) - CodeLens 实例数组的 Promise。

#### `vscode.executeCodeActionProvider` 执行代码操作提供程序

- uri - 文本文档的 Uri
- rangeOrSelection - 文本文档中的范围。一些重构提供者需要选择对象。
- kind - (optional) 返回代码操作的代码操作类型
- itemResolveCount - 要解决的代码操作数（太大会减慢代码操作）
- (returns) - CodeLens 实例数组的 Promise。

#### `vscode.executeDocumentColorProvider` 执行文档颜色提供程序

- uri - 文本文档的 Uri
- (returns) - ColorInformation 对象数组 Promise。

#### `vscode.executeColorPresentationProvider` 执行颜色演示提供程序

- color - 要显示和插入的颜色
- context - 具有 uri 和范围的上下文对象
- (returns) - 解析为一组 ColorPresentation 对象的 Promise

#### `vscode.executeInlayHintProvider` 执行镶嵌提示提供程序

- uri - 文本文档的 Uri
- range - 文本文档中的范围
- (returns) - Inlay 对象数组的 Promise

#### `vscode.resolveNotebookContentProviders` 解析笔记本内容提供程序

- (returns) - NotebookContentProvider 静态信息对象数组的 Promise

#### `vscode.open` 在编辑器中打开提供的资源。可以是文本或二进制文件，也可以是 http(s) URL。如果您需要更多地控制打开文本文件的选项，请改用 `vscode.window.showTextDocument`。

- uri - 文本文档的 Uri
- columnOrOptions - (optional) 要打开的列或编辑器选项，请参阅 `vscode.TextDocumentShowOptions`
- label - (optional)
- (returns) - no result

#### `vscode.openWith` 使用特定编辑器打开提供的资源

- resource - 要打开的资源
- viewId - 自定义编辑器视图 ID 或 `'default'` 以使用 VS Code 的默认编辑器
- columnOrOptions - (optional) 要打开的列或编辑器选项，请参阅 `vscode.TextDocumentShowOptions`
- (returns) - no result

#### `vscode.diff` 在差异编辑器中打开提供的资源以比较它们的内容

- left - 差异编辑器的左侧资源
- right - 差异编辑器的右侧资源
- title - (optional) 差异编辑器的人类可读标题
- columnOrOptions - (optional) 要打开的列或编辑器选项，请参阅 `vscode.TextDocumentShowOptions`
- (returns) - no result

#### `vscode.removeFromRecentlyOpened` 从最近打开的列表中删除具有给定路径的条目。

- path - 从最近打开的路径中删除。

#### `vscode.openIssueReporter` 使用提供的扩展 ID 作为选定源打开问题报告器

- extensionId - 要报告问题的 extensionId 

#### `cursorMove` 将光标移动到视图中的逻辑位置

- 光标移动参数对象 - 可以通过此参数传递的属性值对
    - `'to'`：提供光标移动位置的强制逻辑位置值
    ```
    'left', 'right', 'up', 'down', 'prevBlankLine', 'nextBlankLine',
    'wrappedLineStart', 'wrappedLineEnd', 'wrappedLineColumnCenter'
    'wrappedLineFirstNonWhitespaceCharacter', 'wrappedLineLastNonWhitespaceCharacter'
    'viewPortTop', 'viewPortCenter', 'viewPortBottom', 'viewPortIfOutside'
    ````
    - `'by'`：要移动的单位。默认值是根据 `'to'` 值计算的
    ```
    'line', 'wrappedLine', 'character', 'halfLine'
    ```
    - `'value'`: 要移动的单位数. 默认是 `'1'`
    - `'select'`: 是否选中内容。选中 'true'，默认为 'false'。

#### `editorScroll` 向给定方向滚动编辑器

- 编辑器滚动参数对象 - 可以通过此参数传递的属性值对：
    - `'to'`：强制方向值
    ```
    'up', 'down'
    ```
    - `'by'`：要移动的单位。默认值是根据 `'to'` 值计算的
    ```
    'line', 'wrappedLine', 'page', 'halfPage'
    ```
    - `'value'`：要移动的单位数。默认为 `'1'`。
    - `'revealCursor'`：如果 `'true'` 显示光标，如果它在视口之外。

#### `revealLine` 在给定的逻辑位置显示给定的行

- 显示行参数对象 - 可以通过此参数传递的属性值对：
    - `'lineNumber'`：强制行号值。
    - `'at'`：必须显示行的逻辑位置
    ```
    'top', 'center', 'bottom'
    ```

#### `editor.unfold` 在编辑器中展开内容

- 展开编辑器参数 - 可以通过此参数传递的属性值对：
    - `'levels'`：要展开的关卡数。如果未设置，则默认为 `1`。
    - `'direction'`：如果`'up'`，则向上展开给定的级别数，否则向下展开。
    - `'selectionLines'`：要应用展开操作的编辑器选择的起始行（从 0 开始）。如果未设置，将使用活动选择。


#### `editor.fold` 折叠编辑器中的内容

- 折叠编辑器参数 - 可以通过此参数传递的属性值对
    - `'levels'`：要折叠的级别数。
    - `'direction'`：如果'up'，则向上折叠给定数量的级别，否则向下折叠。
    - `'selectionLines'`：要应用折叠操作的编辑器选择的起始行（从 0 开始）。如果未设置，将使用活动选择。如果未设置级别或方向，则折叠位置处的区域，或者如果已经折叠，则改为使用第一个未折叠的父级。

#### `editor.action.goToLocations` 从文件中的某个位置转到位置

- uri - 开始的文本文档
- position - 开始的位置
- locations - 一组位置
- multiple - 定义当有多个结果时要做什么，可以是 `peek`、`gotoAndPeek` 或 `goto`
- noResultsMessage - 显示位置为空时的人类可读消息。

#### `editor.action.peekLocations` 从文件中的某个位置查看位置

- uri - 开始的文本文档
- position - 开始的位置
- locations - 一组位置
- multiple - 定义当有多个结果时要做什么，可以是 `peek`、`gotoAndPeek` 或 `goto`

#### `workbench.action.quickOpen` 快速访问

- prefix - 字符串值，表示打开时要填写到快速访问输入字段中的值

#### `moveActiveEditor` 按选项卡或组移动活动编辑器

- 活动编辑器移动参数 - 参数属性：
    - `'to'`：提供移动位置的字符串值。
    - `'by'`：提供移动单位的字符串值（按 `tab ` 或按 `group`）。
    - `'value'`：数字值，提供要移动的位置数或绝对位置。

#### `vscode.setEditorLayout` 设置编辑器布局。

- layout - 要设置的编辑器布局。

布局被描述为具有初始（可选）方向（0 = 水平，1 = 垂直）和其中的编辑器组数组的对象。每个编辑器组可以有一个大小和另一个编辑器组数组，它​​们将与方向正交。如果提供了编辑器组大小，则它们的总和必须为 1 才能应用于每行或每列。 2x2 网格示例：`{ orientation: 0, groups: [{ groups: [{}, {}], size: 0.5 }, { groups: [{}, {}], size: 0.5 }] }`

#### `notebook.cell.execute` 执行单元格

- range - 单元格范围
- uri - 文档 uri

#### `notebook.cell.cancelExecution` 停止单元执行

- range - 单元格范围
- uri - 文档 uri

#### `notebook.execute` 执行笔记本

- uri - 文档 uri

#### `notebook.cancelExecution` 取消执行笔记本

- uri - 文档 uri

#### `notebook.fold` 折叠单元格

- index - 单元格索引

#### `notebook.unfol` 展开单元格

- index - 单元格索引

#### `notebook.selectKernel` 笔记本内核参数

- kernelInfo - The kernel info

#### `search.action.openNewEditor` 打开一个新的搜索编辑器。传递的参数可以包括像 ${relativeFileDirname} 这样的变量。

- 打开新的搜索编辑器 args -

#### `search.action.openEditor` 打开一个新的搜索编辑器。传递的参数可以包括像 ${relativeFileDirname} 这样的变量。

- 打开新的搜索编辑器 args -

#### `search.action.openNewEditorToSide` 打开一个新的搜索编辑器。传递的参数可以包括像 ${relativeFileDirname} 这样的变量。

- 打开新的搜索编辑器 args -

#### `vscode.openFolder` 根据 newWindow 参数在当前窗口或新窗口中打开文件夹或工作区。请注意，除非 newWindow 参数设置为 true，否则在同一窗口中打开将关闭当前扩展主机进程并在给定文件夹/工作区上启动一个新进程。

- uri - (optional) 要打开的文件夹或工作区文件的 Uri。如果未提供，本机对话框将询问用户文件夹
- options - (optional) Object with the following properties: 
    - `forceNewWindow`：是否在新窗口中打开文件夹/工作区或相同。默认为在同一窗口中打开。
    - `noRecentEntry`：打开的 URI 是否会出现在“打开最近的”列表中。默认为 `true`。

    注意，为了向后兼容，选项也可以是布尔类型，表示 `forceNewWindow` 设置。


#### `workbench.extensions.installExtension` 安装给定的扩展

- 扩展 ID 或 VSIX 资源 uri -

#### `workbench.extensions.uninstallExtension` 卸载给定的扩展

- 要卸载的扩展程序的 ID -

#### `workbench.extensions.search` 搜索特定的扩展

- Query to use in search -

#### `workbench.action.files.newUntitledFile` 新的无标题文件

- viewType - The editor view type

#### `workbench.action.findInFiles` - 打开搜索视图

- 搜索视图的一组选项 -

## 简单的命令

不需要参数的简单命令可以在默认 `keybindings.json` 文件的键盘快捷键列表中找到。未绑定的命令列在文件底部的注释块中。

<br>

查看 `keybindings.json`：

- Windows, Linux: **File** > **Preferences** > Keyboard** Shortcuts** > `keybindings.json` link
- macOS: **Code** > **Preferences** > **Keyboard Shortcuts** > `keybindings.json` link

## 附录 

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。