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
        <td><code>explorerResourceIsFolder</code></td><td>如果在资源管理器中选择了文件夹，则为真。</td>
    </tr>
    <tr>
        <td colspan="2">编辑器小部件上下文</td>
    </tr>
    <tr>
        <td><code>explorerViewletVisible</code></td><td>如果资源管理器视图可见，则为真。</td>
        <td><code>explorerViewletFocus</code></td><td>如果资源管理器视图具有键盘焦点，则为真。</td>
        <td><code>filesExplorerFocus</code></td><td>如果文件资源管理器部分具有键盘焦点，则为真。</td>
        <td><code>openEditorsFocus</code></td><td>如果 OPEN EDITORS 部分具有键盘焦点，则为真。</td>
        <td><code>explorerResourceIsFolder</code></td><td>如果在资源管理器中选择了文件夹，则为真。</td>
        <td><code>explorerResourceIsFolder</code></td><td>如果在资源管理器中选择了文件夹，则为真。</td>
    </tr>
</table>

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。