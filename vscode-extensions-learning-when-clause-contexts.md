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

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。