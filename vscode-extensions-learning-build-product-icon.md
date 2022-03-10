# VSCode 产品图标参考

Visual Studio Code 包含一组用于视图和编辑器的内置图标，但也可用于悬停、状态栏和扩展。这些图标是 **产品图标**，而不是 **文件图标**，**文件图标** 用于整个 UI 中的文件名旁边。

<br>

VS Code 附带的产品图标包含在 [Codicon 图标字体](https://github.com/microsoft/vscode-codicons)中，并形成默认的产品图标主题。扩展可以提供新的[产品图标主题](https://code.visualstudio.com/api/extension-guides/product-icon-theme)来重新定义这些图标并赋予 VS Code 新的外观。

<br>

为了实现这一点，所有产品图标都由 **ID** 标识。图标标识符用于 UI 组件中的 **labels** (`$(pencil)`)、API 中的 `ThemeIcon` 以及需要图标时的贡献。

<br>

图标标识符与实际图标字体字形的关联发生在产品图标主题中。

<br>

> [官网文档](https://code.visualstudio.com/api/references/icons-in-labels)

## Icons in labels

图标可用于悬停的 Markdown 标签、[StatusBarItem](https://code.visualstudio.com/api/references/vscode-api#StatusBarItem) 文本和 [QuickPickItem](https://code.visualstudio.com/api/references/vscode-api#QuickPickItem) 标签 API。在 Markdown 中添加图标的语法是 `$(iconIdentifier)`：

<br>

```
$(alert);
```

<br>

您还可以嵌入文本并使用多个图标：

<br>

```
$(eye) $(heart) $(mark-github) GitHub
```

<br>

要将文字 `${...}` 文本放在标签内，请使用反斜杠转义 `$`：

<br>

```
\$(eye)
```

## 动画

您可以通过将 `~spin` 附加到图标名称来将旋转动画应用于以下图标：

- `sync`
- `loading`
- `gear`

```
$(sync~spin)
```

## 图标贡献点

图标贡献点允许扩展通过 ID 定义附加图标以及默认图标。然后，图标 ID 可以由标签 (`$(iconId)`) 中的扩展程序（或依赖于扩展程序的任何其他扩展程序）或可以使用 `ThemeIcon` 的所有位置（`new ThemeIcon("iconId")`）使用。

<br>

```
"contributes": {
  "icons": {
        "distro-ubuntu": {
            "description": "Ubuntu icon",
            "default": {
                "fontPath": "./distroicons.woff",
                "fontCharacter": "\\E001"
            }
        },
        "distro-fedora": {
            "description": "Ubuntu icon",
            "default": {
                "fontPath": "./distroicons.woff",
                "fontCharacter": "\\E002"
            }
        }
    }
}
```

<br>

产品图标主题可以重新定义图标（如果他们知道图标 ID）。

## [Icon Listing](https://code.visualstudio.com/api/references/icons-in-labels#icon-listing)

下面是按标识符列出的内置产品图标。

<br>

图标的 ID 标识了使用图标的位置。默认的 codicon ID 描述了默认使用来自 codicon 库的哪个图标，并且预览会显示该图标的外观。

<br>

[产品图标主题](https://code.visualstudio.com/api/extension-guides/product-icon-theme)可以单独替换每个图标，以及来自 codicon 库的所有图标。


## 附录 

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。