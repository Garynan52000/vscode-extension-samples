# VSCode 扩展清单

每个 Visual Studio Code 扩展都需要一个位于扩展目录结构根目录的清单文件 `package.json`。

<br>

> [官网文档](https://code.visualstudio.com/api/references/extension-manifest)

## 字段

<table style="text-align: center;">
    <tr>
        <th>Name</th><th>Required</th><th>Type</th><th>Details</th>
    </tr>
    <tr>
        <td><code>name</code></td>
        <td>YES</td>
        <td><code>string</code></td>
        <td>扩展的名 - 应该全部小写且没有空格。</td>
    </tr>
    <tr>
        <td><code>version</code></td>
        <td>YES</td>
        <td><code>string</code></td>
        <td><a href="https://semver.org/" target="_blank">SemVer</a> 兼容版本。</td>
    </tr>
    <tr>
        <td><code>engines</code></td>
        <td>YES</td>
        <td><code>object</code></td>
        <td>至少包含与扩展<a href="https://code.visualstudio.com/api/working-with-extensions/publishing-extension#visual-studio-code-compatibility" target="_blank">兼容的</a> VS Code 版本匹配的 <code>vscode</code> 键的对象。不可能是 <code>*</code>。例如：<code>^0.10.5</code> 表示与最低 VS Code 版本 <code>0.10.5</code> 的兼容性。</td>
    </tr>
    <tr>
        <td><code>publisher</code></td>
        <td>YES</td>
        <td><code>string</code></td>
        <td><a href="https://code.visualstudio.com/api/working-with-extensions/publishing-extension#publishing-extensions" target="_blank">出版商</a>名称。</td>
    </tr>
    <tr>
        <td><code>license</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>请参阅 <a href="https://code.visualstudio.com/api/working-with-extensions/publishing-extension#publishing-extensions" target="_blank">npm 的文档</a>。如果您在扩展的根目录中确实有一个 <code>LICENSE</code> 文件，<code>license</code>的值应该是<code>"SEE LICENSE IN &lt;filename&gt;"</code>。</td>
    </tr>
    <tr>
        <td><code>displayName</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>市场中使用的扩展程序的显示名称。</td>
    </tr>
    <tr>
        <td><code>description</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>简短描述您的扩展是什么和做什么。</td>
    </tr>
    <tr>
        <td><code>categories</code></td>
        <td></td>
        <td><code>string[]</code></td>
        <td>您要用于扩展的类别。允许值：<code>[Programming Languages, Snippets, Linters, Themes, Debuggers, Formatters, Keymaps, SCM Providers, Other, Extension Packs, Language Packs, Data Science, Machine Learning, Visualization, Notebooks, Education, Testing]</code></td>
    </tr>
    <tr>
        <td><code>keywords</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>一组<b>关键字</b>，可以更轻松地找到扩展程序。这些包含在市场上的其他扩展<b>标签</b>中。此列表目前仅限于 5 个关键字。</td>
    </tr>
    <tr>
        <td><code>galleryBanner</code></td>
        <td></td>
        <td><code>object</code></td>
        <td>帮助格式化 Marketplace 标题以匹配您的图标。请参阅下面的详细信息。</td>
    </tr>
    <tr>
        <td><code>preview</code></td>
        <td></td>
        <td><code>boolean</code></td>
        <td>将扩展设置为在市场中标记为预览。</td>
    </tr>
    <tr>
        <td><code>main</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>扩展程序的入口文件。</td>
    </tr>
    <tr>
        <td><code>browser</code></td>
        <td></td>
        <td><code>string</code></td>
        <td><a href="https://code.visualstudio.com/api/extension-guides/web-extensions" target="_blank">Web 扩展</a>的入口文件。</td>
    </tr>
    <tr>
        <td><code>contributes</code></td>
        <td></td>
        <td><code>object</code></td>
        <td>描述<a href="https://code.visualstudio.com/api/references/contribution-points" target="_blank">扩展贡献</a>的对象。</td>
    </tr>
    <tr>
        <td><code>activationEvents</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>此扩展的<a href="https://code.visualstudio.com/api/references/activation-events" target="_blank">激活事件</a>数组。</td>
    </tr>
    <tr>
        <td><code>badges</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>显示在 Marketplace 扩展页面侧边栏中的<a href="https://code.visualstudio.com/api/references/extension-manifest#approved-badges" target="_blank">已批准徽章</a>数组。</td>
    </tr>
    <tr>
        <td><code>markdown</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>控制 Marketplace 中使用的 Markdown 渲染引擎。github（默认）或标准。 </td>
    </tr>
    <tr>
        <td><code>qna</code></td>
        <td></td>
        <td><code>marketplace (default), string, false</code></td>
        <td>控制市场中的<b>Q & A </b>链接。github（默认）或标准。设置为 <code>marketplace</code> 以启用默认市场问答网站。设置为 <code>string</code> 以提供自定义问答网站的 URL。设置为 <code>false</code> 以完全禁用问答。</td>
    </tr>
    <tr>
        <td><code>dependencies</code></td>
        <td></td>
        <td><code>object</code></td>
        <td>您的扩展需要的任何运行时 Node.js 依赖项。和 <a href="https://docs.npmjs.com/cli/v7/configuring-npm/package-json#dependencies" target="_blank">npm 的 <code>dependencies</code></a>完全一样。</td>
    </tr>
    <tr>
        <td><code>devDependencies</code></td>
        <td></td>
        <td><code>object</code></td>
        <td>您的扩展需要的任何开发 Node.js 依赖项。和 <a href="https://docs.npmjs.com/cli/v7/configuring-npm/package-json#devdependencies" target="_blank">npm 的 <code>devDependencies</code></a>完全一样。</td>
    </tr>
    <tr>
        <td><code>extensionPack</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>包含与此扩展<b>捆绑</b>的扩展 ID 的数组。这些其他扩展将在安装主扩展时安装。 扩展的 id 总是 <code>${publisher}.${name}</code>。例如：<code>vscode.csharp</code>。</td>
    </tr>
    <tr>
        <td><code>extensionDependencies</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>具有此扩展所<b>依赖</b>的扩展 ID 的数组。这些其他扩展将在安装主扩展时安装。扩展的 id 总是 <code>${publisher}.${name}</code>。例如：<code>vscode.csharp</code>。</td>
    </tr>
    <tr>
        <td><code>extensionKind</code></td>
        <td></td>
        <td><code>array</code></td>
        <td>指示扩展应在远程配置中运行的位置的数组。值是 <code>ui</code>（在本地运行）、<code>workspace</code>（在远程机器上运行）或两者，按顺序设置首选项。例如：<code>[ui, workspace]</code> 表示扩展可以在任一位置运行，但更喜欢在本地计算机上运行。有关更多详细信息，请参见<a href="https://code.visualstudio.com/api/advanced-topics/extension-host#preferred-extension-location" target="_blank">此处</a>。</td>
    </tr>
    <tr>
        <td><code>scripts</code></td>
        <td></td>
        <td><code>object</code></td>
        <td>与 <a href="https://docs.npmjs.com/misc/scripts" target="_blank">npm 的 <code>scripts</code></a> 完全相同，但具有额外的 VS Code 特定字段，例如 <a href="https://code.visualstudio.com/api/working-with-extensions/publishing-extension#prepublish-step" target="_blank">vscode:prepublish</a> 或 <a href="https://code.visualstudio.com/api/references/extension-manifest#extension-uninstall-hook" target="_blank">vscode:uninstall</a>。</td>
    </tr>
    <tr>
        <td><code>icon</code></td>
        <td></td>
        <td><code>string</code></td>
        <td>至少 128x128 像素（Retina 屏幕为 256x256）图标的路径。</td>
    </tr>
</table>

<br>

还可以检查 [npm 的 package.json 参考](https://docs.npmjs.com/cli/v7/configuring-npm/package-json)

```
# Here is a complete package.json

{
  "name": "wordcount",
  "displayName": "Word Count",
  "version": "0.1.0",
  "publisher": "ms-vscode",
  "description": "Markdown Word Count Example - reports out the number of words in a Markdown file.",
  "author": {
    "name": "sean"
  },
  "categories": ["Other"],
  "icon": "images/icon.png",
  "galleryBanner": {
    "color": "#C80000",
    "theme": "dark"
  },
  "activationEvents": ["onLanguage:markdown"],
  "engines": {
    "vscode": "^1.0.0"
  },
  "main": "./out/extension",
  "scripts": {
    "vscode:prepublish": "node ./node_modules/vscode/bin/compile",
    "compile": "node ./node_modules/vscode/bin/compile -watch -p ./"
  },
  "devDependencies": {
    "@types/vscode": "^0.10.x",
    "typescript": "^1.6.2"
  },
  "license": "SEE LICENSE IN LICENSE.txt",
  "bugs": {
    "url": "https://github.com/microsoft/vscode-wordcount/issues",
    "email": "sean@contoso.com"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/microsoft/vscode-wordcount.git"
  },
  "homepage": "https://github.com/microsoft/vscode-wordcount/blob/main/README.md"
}
```

## 市场展示技巧

这里有一些提示和建议，可以让你的扩展在 [VS Code Marketplace](https://marketplace.visualstudio.com/VSCode) 上展示时看起来很棒。

<br>

始终使用最新的 `vsce` 所以 `npm install -g vsce` 以确保您拥有它。

<br>

在扩展程序的根文件夹中有一个 `README.md` Markdown 文件，我们会将内容包含在扩展程序详细信息的正文中（在市场上）。您可以在 `README.md` 中提供相对路径图像链接。

<br>

这里有一些例子：

- [Word Count](https://marketplace.visualstudio.com/items?itemName=ms-vscode.wordcount)
- [MD Tools](https://marketplace.visualstudio.com/items/seanmcbreen.MDTools)

**提供一个好的显示名称和描述**。这对于市场和产品展示很重要。这些字符串也用于 VS Code 中的文本搜索，并且拥有相关的关键字会有很大帮助。

<br>

```
    "displayName": "Word Count",
    "description": "Markdown Word Count Example - reports out the number of words in a Markdown file.",
```

<br>

**图标和对比鲜明的横幅颜色**在 Marketplace 页面标题上看起来很棒。`theme` 属性是指要在横幅中使用的字体 - 深色或浅色。

<br>

```
{
  "icon": "images/icon.png",
  "galleryBanner": {
    "color": "#C80000",
    "theme": "dark"
  }
}
```

<br>

您可以**设置几个可选链接**（`bugs`, `homepage`, `repository`），这些链接显示在 Marketplace 的 **Resources** 部分下。

<br>

```
{
  "license": "SEE LICENSE IN LICENSE.txt",
  "homepage": "https://github.com/microsoft/vscode-wordcount/blob/main/README.md",
  "bugs": {
    "url": "https://github.com/microsoft/vscode-wordcount/issues",
    "email": "sean@contoso.com"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/microsoft/vscode-wordcount.git"
  }
}
```

<br>

<table>
    <tr>
        <th>Marketplace Resources link</th><th>package.json attribute</th>
    </tr>
    <tr>
        <td>Issues</td><td><code>bugs:url</code></td>
        <td>Repository</td><td><code>repository:url</code></td>
        <td>Homepage</td><td><code>homepage</code></td>
        <td>License</td><td><code>license</code></td>
    </tr>
</table>

<br>

**为您的扩展设置一个 `category` 类别**。同一类别的扩展在市场上分组在一起，从而改进了过滤和发现。

<br>

> 注意：仅使用对您的扩展有意义的值。允许的值为 `[Programming Languages, Snippets, Linters, Themes, Debuggers, Formatters, Keymaps, SCM Providers, Other, Extension Packs, Language Packs, Data Science, Machine Learning, Visualization, Notebooks, Education, Testing]`。将 `Programming Languages` 用于一般语言功能，如语法突出显示和代码完成。`Language Packs` 类别保留用于显示语言扩展（例如，本地化的保加利亚语）。

#### 批准的徽章

出于安全考虑，我们只允许来自受信任服务的徽章。我们允许来自以下 URL 前缀的徽章：

- api.bintray.com
- api.travis-ci.com
- api.travis-ci.org
- app.fossa.io
- badge.buildkite.com
- badge.fury.io
- badge.waffle.io
- badgen.net
- badges.frapsoft.com
- badges.gitter.im
- badges.greenkeeper.io
- cdn.travis-ci.com
- cdn.travis-ci.org
- ci.appveyor.com
- circleci.com
- cla.opensource.microsoft.com
- codacy.com
- codeclimate.com
- codecov.io
- coveralls.io
- david-dm.org
- deepscan.io
- dev.azure.com
- docs.rs
- flat.badgen.net
- gemnasium.com
- githost.io
- github.com (from Workflows only)
- gitlab.com
- godoc.org
- goreportcard.com
- img.shields.io
- isitmaintained.com
- marketplace.visualstudio.com
- nodesecurity.io
- opencollective.com
- snyk.io
- travis-ci.com
- travis-ci.org
- visualstudio.com
- vsmarketplacebadge.apphb.com
- www.bithound.io
- www.versioneye.com

如果您有其他想要使用的徽章，请打开 [GitHub 问题](https://github.com/microsoft/vscode/issues)。

## 结合扩展贡献

`yo code` 生成器让您轻松打包 TextMate 主题，着色器和代码片段并创建新的扩展。当生成器运行时，它会为每个选项创建一个完整的独立扩展包。但是，拥有一个组合多个贡献的单个扩展通常更方便。例如，如果您要添加对一种新语言的支持，您希望为用户提供带有着色的语言定义以及片段，甚至可能是调试支持。

<br>

要合并扩展贡献，请编辑现有扩展清单 `package.json` 并添加新贡献和关联文件。

<br>

下面是一个扩展清单，其中包括 LaTex 语言定义（语言标识符和文件扩展名）、着色（语法）和片段。

<br>

```
{
  "name": "language-latex",
  "description": "LaTex Language Support",
  "version": "0.0.1",
  "publisher": "someone",
  "engines": {
    "vscode": "0.10.x"
  },
  "categories": ["Programming Languages", "Snippets"],
  "contributes": {
    "languages": [
      {
        "id": "latex",
        "aliases": ["LaTeX", "latex"],
        "extensions": [".tex"]
      }
    ],
    "grammars": [
      {
        "language": "latex",
        "scopeName": "text.tex.latex",
        "path": "./syntaxes/latex.tmLanguage.json"
      }
    ],
    "snippets": [
      {
        "language": "latex",
        "path": "./snippets/snippets.json"
      }
    ]
  }
}
```

<br>

请注意，扩展清单 `categories` 属性现在包括 `Programming Languages` 和 `Snippets`，以便在市场上轻松发现和过滤。

<br>

> 提示：确保您的合并贡献使用相同的标识符。在上面的示例中，所有三个贡献都使用 “latex” 作为语言标识符。这让 VS Code 知道着色器（`grammars`）和片段用于 LaTeX 语言，并且在编辑 LaTeX 文件时将处于活动状态。

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。