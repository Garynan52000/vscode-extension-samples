# VSCode 拓展清单中的各个贡献点

Contribution Points - 是您在 `package.json` [扩展清单](https://code.visualstudio.com/api/references/extension-manifest)的贡献字段中进行的一组 JSON 声明。您的扩展注册贡献点以扩展 Visual Studio Code 中的各种功能。

<br>

> [官网文档](https://code.visualstudio.com/api/references/contribution-points#contributes.breakpoints)

## [contributes.breakpoints](https://code.visualstudio.com/api/references/contribution-points#contributes.breakpoints)

通常调试器扩展也会有一个 `contributors.breakpoints` 条目，其中扩展列出了将启用设置断点的语言文件类型。

## [contributes.colors](https://code.visualstudio.com/api/references/contribution-points#contributes.colors)

提供新的主题颜色。这些颜色可以被编辑器装饰器和状态栏中的扩展使用。一旦定义，用户可以在 `workspace.colorCustomization` 设置中自定义颜色，用户主题可以设置颜色值。

<br>

可以为颜色默认值定义浅色、深色和高对比度的主题颜色，并且可以是对现有颜色的引用或[颜色十六进制值](https://code.visualstudio.com/api/references/theme-color#color-formats)。

<br>

扩展可以使用 ThemeColor API 使用新的和现有的主题颜色：

<br>

```
const errorColor = new vscode.ThemeColor('superstatus.error');
```

## [contributes.commands](https://code.visualstudio.com/api/references/contribution-points#contributes.commands)

默认情况下，命令显示在命令面板 (`Ctrl+Shift+P`)，但它们也可以显示在[其他菜单](https://code.visualstudio.com/api/references/contribution-points#contributes.menus)中

<br>

> 注意：当调用命令时（从键绑定、命令面板、任何其他菜单或以编程方式），VS Code 将发出一个 [activationEvent `onCommand:${command}`](https://code.visualstudio.com/api/references/activation-events#onCommand)。

<br>

> 注意：使用 [product icons](https://code.visualstudio.com/api/references/icons-in-labels#icon-listing) 中的图标时，设置 `light` 和 `dark` 将禁用图标。正确的语法是 `"icon": "$(book)"`

#### Command 图标的格式

- 尺寸: 图标应为 16x16，内边距为 1 像素（图像为 14x14）并居中
- 颜色: 图标应使用单一颜色。
- 格式: 尽管接受任何图像文件类型，但建议使用 SVG 图标。

## [contributes.configuration](https://code.visualstudio.com/api/references/contribution-points#contributes.configuration)

贡献的配置密钥是向用户公开的。通过使用设置编辑器或直接编辑 JSON 设置文件，用户将能够将这些配置选项设置为用户设置或工作区设置。

<br>

此部分可以是单个对象，表示单个设置类别，也可以是对象数组，表示多个设置类别。如果有多个类别的设置，设置编辑器将在该扩展的目录中显示一个子菜单，并且标题键将用于子菜单条目名称

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/configuration.png)

<br>

您可以使用从您的扩展程序中读取这些值

<br>

```
vscode.workspace.getConfiguration('myExtension')
```

#### Configuration schema

您声明的 Configuration 配置既用于在 JSON 编辑器中编辑设置时提供智能提示，也用于定义它们在设置 UI 中的显示方式。

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/settings-ui.png)

<br>

###### title

类别的 `title` 1️⃣️ 是用于该类别的标题。

<br>

```
{
  "configuration": {
    "title": "GitMagic"
  }
}
```

<br>

注意，如果扩展有多个分类的扩展，并且其中一个分类的标题与扩展显示名称相同，然后该类别的设置将直接放置在主扩展标题下方，无论 `order` 字段如何设置。

<br>

对于 `title` 和 `displayName` 字段，“Extension”、“Configuration”和“Settings”之类的词都是多余的。

- ✔ "title": "GitMagic"
- ❌ "title": "GitMagic Extension"
- ❌ "title": "GitMagic Configuration"
- ❌ "title": "GitMagic Extension Configuration Settings"

###### properties

配置中的 `properties` 2️⃣ 将是配置属性的字典。

<br>

在设置 UI 中，您配置 `properties` 的 key 将用于命名空间和构造标题。尽管扩展可以包含多个类别的设置，但扩展的每个设置仍然必须有自己的唯一的 key。key 中的大写字母用于表示分词。例如，如果您的 key 是 `gitMagic.blame.dateFormat`，则生成的设置标题将如下所示：

<br>

> Blame: Date Format

<br>

条目将根据您的密钥中建立的层次结构进行分组。例如，这些条目

<br>

```
gitMagic.blame.dateFormat
gitMagic.blame.format
gitMagic.blame.heatMap.enabled
gitMagic.blame.heatMap.location
```

<br>

将出现在一个组中，如下所示：

<br>

> Blame: Date Format <br> Blame: Format <br> Blame › Heatmap: Enabled <br> Blame › Heatmap: Location

<br>

此外，没有明确 `order` 字段的 properties **按字母顺序显示**（不是它们在清单中列出的顺序）。

#### Configuration property schema

配置的 keys 是使用 [JSON Schema](https://json-schema.org/understanding-json-schema/reference/index.html) 的超集定义的。

###### description / markdownDescription

您的描述 3️⃣ 出现在标题之后和输入字段之前，布尔值除外，其中描述用作复选框的标签。 6️⃣

<br>

```
{
  "gitMagic.blame.heatmap.enabled": {
    "description": "Specifies whether to provide a heatmap indicator in the gutter blame annotations"
  }
}
```

<br>

如果您使用 `markdownDescription` 而不是 `description`，您的设置描述将在设置 UI 中呈现为 Markdown。

<br>

```
{
  "gitMagic.blame.dateFormat": {
    "markdownDescription": "Specifies how to format absolute dates (e.g. using the `${date}` token) in gutter blame annotations. See the [Moment.js docs](https://momentjs.com/docs/#/displaying/format/) for valid formats"
  }
}
```

###### type

`number` 4️⃣ 、 `string` 5️⃣ 、 `boolean` 6️⃣ 类型的条目可以直接在设置 UI 中进行编辑。

<br>

```
{
  "gitMagic.views.pageItemLimit": {
    "type": "number",
    "default": 20,
    "markdownDescription": "Specifies the number of items to show in each page when paginating a view list. Use 0 to specify no limit"
  }
}
```

<br>

如果在配置条目上设置`"editPresentation": "multilineText"`，则可以使用多行文本输入呈现字符串设置。

<br>

对于 `boolean` 条目，描述（或 markdownDescription）将用作复选框的标签。

<br>

```
{
  "gitMagic.blame.compact": {
    "type": "boolean",
    "description": "Specifies whether to compact (deduplicate) matching adjacent gutter blame annotations"
  }
}
```

<br>

一些 `object` 和 `array` 类型设置将在设置 UI 中呈现。`number`、`string` 或 `booelan` 的简单数组将呈现为可编辑列表。具有 `string`、 `number`、 `integer` 和/或 `boolean` 类型的属性对象将呈现为 key:value 的可编辑网格。对象设置还应将 `additionalProperties` 设置为 `false`，或者是 `object` 类型具有适当 `type` 属性，以在 UI 中呈现。

<br>

如果 `object` 或 `array` 类型设置还可以包含其他类型，如嵌套对象、数组或 `null`，那么该值将不会在设置 UI 中呈现，只能通过直接编辑 JSON 来修改。用户将在 **settings.json** 中看到一个编辑链接，如上面的屏幕截图所示。 8️⃣

###### order

类别和这些类别中的设置都可以采用整数类型的 `order` 属性，该属性提供了它们应如何相对于其他类别和/或设置进行排序的参考。

<br>

如果两个类别具有 `order` 属性，则**顺序号较低的类别先出现**。如果一个类别没有被赋予顺序属性，它会出现在被赋予该属性的类别之后

<br>

如果同一类别中的两个设置具有顺序属性，则顺序号较低的设置在前。序号较低的设置在前。如果同一类别中的另一个设置没有被赋予 `order` 属性，它将出现在该类别中被赋予该属性的设置之后。

<br>

如果两个类别具有相同的 `order` 属性值，或者如果同一类别中的两个设置具有相同的 `order` 属性值，则它们将在设置 UI 中按字母顺序升序排序。

###### enum / enumDescriptions

如果您在枚举 7️⃣ 属性下提供一组项目，设置 UI 将呈现一个下拉菜单。

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/settings-ui-enum.png)

<br>

您还可以提供一个 `enumDescriptions` 属性，该属性提供在下拉列表底部呈现的描述性文本：

###### deprecationMessage / markdownDeprecationMessage

如果设置 `deprecationMessage` 或 `markdownDeprecationMessage` 该设置将收到带有您指定消息的警告下划线。除非由用户配置，否则它不会显示在设置 UI 中。如果设置了 `markdownDeprecationMessage`，markdown 将不会在设置悬停或问题视图中呈现，并且 `markdownDeprecationMessage` 将在设置 UI 中呈现为 Markdown。 例子：

<br>

```
{
  "json.colorDecorators.enable": {
    "type": "boolean",
    "description": "Enables or disables color decorators",
    "markdownDeprecationMessage": "**Deprecated**: Please use `#editor.colorDecorators#` instead.",
    "deprecationMessage": "Deprecated: Please use editor.colorDecorators instead."
  }
}
```

<br>

###### Other JSON Schema properties

您可以使用任何验证 JSON Schema 属性来描述配置值的其他约束：

- `default` 用于定义属性的默认值
- `minimum` 和 `maximum` 用于限制数值
- `maxLength`, `minLength` 用于限制字符串长度
- `pattern` 用于将字符串限制为给定的正则表达式
- `patternErrorMessage` 用于在模式不匹配时提供量身定制的错误消息
- `format` 用于将字符串限制为众所周知的格式, 例如 `date`, `time`, `ipv4`, `email`, 还有 `uri`
- `maxItems`, `minItems` 或限制数组长度
- `editPresentation` 用于控制是否为设置编辑器中的字符串设置呈现单行输入框或多行文本区域

###### Unsupported JSON Schema properties

配置部分不支持的是：

- `$ref` 和 `definition`: 配置模式需要是自包含的，并且不能假设聚合设置 JSON 模式文档的外观。关这些和其他功能的更多详细信息，请参阅 [JSON 架构参考](https://json-schema.org/understanding-json-schema/reference/index.html)。

###### scope

配置设置可以具有以下可能的范围之一：

- `application` - 适用于所有 VS Code 实例的设置，只能在用户设置中进行配置。
-`machine` - 只能在用户设置或远程设置中设置的机器特定设置。例如，不应跨机器共享的安装路径。
- `machine-overridable` - 可以被工作区或文件夹设置覆盖的机器特定设置。
- `window` - 可以在用户、工作区或远程设置中配置的 Windows（实例）特定设置。
- `resource` - 资源设置，适用于文件和文件夹，可以在所有设置级别进行配置，甚至是文件夹设置。
- `language-overridable` - 可以在语言级别覆盖的资源设置。

配置范围确定用户何时可以通过设置编辑器使用设置以及该设置是否适用。如果没有声明 `scope`，则默认为 `window`。

<br>

```
{
  "contributes": {
    "configuration": {
      "title": "Git",
      "properties": {
        "git.alwaysSignOff": {
          "type": "boolean",
          "scope": "resource",
          "default": false,
          "description": "%config.alwaysSignOff%"
        },
        "git.ignoredRepositories": {
          "type": "array",
          "default": [],
          "scope": "window",
          "description": "%config.ignoredRepositories%"
        },
        "git.autofetch": {
          "type": ["boolean", "string"],
          "enum": [true, false, "all"],
          "scope": "resource",
          "markdownDescription": "%config.autofetch%",
          "default": false,
          "tags": ["usesOnlineServices"]
        }
      }
    }
  }
}
```

<br>

您可以看到 `git.alwaysSignOff` 具有 `resource` 的 `scope`，并且可以按用户、工作区或文件夹进行设置，而具有 `window` 范围的已忽略存储库列表更适用于 VS Code 窗口或工作区（可能是多根）。

###### Linking to settings

您可以通过在 markdown-type 属性中使用以下特殊语法：`#target.setting.id#`，插入指向另一个设置的链接，该链接将在设置 UI 中呈现为可点击的链接。这将适用于 `markdownDescription`、`markdownEnumDescriptions` 和 `markdownDeprecationMessage`。例子：

<br>

```
 "files.autoSaveDelay": {
    "markdownDescription": "Controls the delay in ms after which a dirty editor is saved automatically. Only applies when `#files.autoSave#` is set to `afterDelay`.",
    // ...
  }
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/setting-link.png)

## contributes.configurationDefaults

提供默认的特定于语言的编辑器配置。这将覆盖所提供语言的默认编辑器配置。

<br>

以下示例提供了 `markdown` 语言的默认编辑器配置

<br>

```
{
  "contributes": {
    "configurationDefaults": {
      "[markdown]": {
        "editor.wordWrap": "on",
        "editor.quickSuggestions": false
      }
    }
  }
}
```

## contributes.customEditors

[`customEditors`](https://code.visualstudio.com/api/extension-guides/custom-editors) 贡献点是您的扩展如何告诉 VS Code 它提供的自定义编辑器。例如，VS Code 需要知道您的自定义编辑器使用哪些类型的文件，以及如何在任何 UI 中识别您的自定义编辑器。

<br>

这是 [`customEditor` 扩展示例](https://github.com/microsoft/vscode-extension-samples/tree/main/custom-editor-sample)的基本 `customEditor` 贡献：

<br>

```
"contributes": {
  "customEditors": [
    {
      "viewType": "catEdit.catScratch",
      "displayName": "Cat Scratch",
      "selector": [
        {
          "filenamePattern": "*.cscratch"
        }
      ],
      "priority": "default"
    }
  ]
}
```

<br>

`customEditors` 是一个数组，因此您的扩展可以贡献多个自定义编辑器。

- `viewType` - 您的自定义编辑器的唯一标识符。
这就是 VS Code 如何将 package.json 中的自定义编辑器贡献与代码中的自定义编辑器实现联系起来。这在所有扩展中必须是唯一的，因此不要使用诸如 “preview” 之类的通用视图类型，请确保使用您的扩展唯一的视图类型，例如 `"viewType": "myAmazingExtension.svgPreview"`。
- `displayName` - 在 VS Code 的 UI 中标识自定义编辑器的名称。
显示名称在 VS Code UI 中显示给用户，例如 **View: Reopen with dropdown。**
- `selector` - 指定自定义编辑器对哪些文件处于活动状态。
`selector` 是一个或多个 glob 模式的数组。这些 glob 模式与文件名相匹配，以确定自定义编辑器是否可以用于它们。诸如 *.png 之类的文件名模式将为所有 PNG 文件启用自定义编辑器。您还可以创建与文件或目录名称匹配的更具体的模式，例如 `**/translations/*`.json。
- `priority` - （可选）指定何时使用自定义编辑器。
    - `"default"` - 尝试对匹配 `selector` 的每个文件使用自定义编辑器。
    - `"option"` - 默认情况下不要使用自定义编辑器，但允许用户切换到它或将其配置为默认值。

## contributes.debuggers

为 VS Code 贡献一个调试器。调试器贡献具有以下属性：

- `type` 是用于在启动配置中标识此调试器的唯一 ID。
- `label` 是此调试器在 UI 中的用户可见名称。
- `program` 针对实际调试器或运行时实现 VS Code 调试协议的调试适配器的路径。
- `runtime` 如果调试适配器的路径不是可执行文件但需要运行时。
- `configurationAttributes` 是特定于此调试器的启动配置参数的架构。请注意，不支持 JSON 模式构造 `$ref` 和 `definition`。
- `initialConfigurations ` 列出用于填充初始 launch.json 的启动配置。
- `configurationSnippets ` 列出在编辑 launch.json 时可通过 IntelliSense 获得的启动配置。
- `variables` 引入替换变量并将它们绑定到调试器扩展实现的命令。
- `languages` 调试扩展可以被视为“默认调试器”的那些语言。 调试器前。

```
{
  "contributes": {
    "debuggers": [
      {
        "type": "node",
        "label": "Node Debug",

        "program": "./out/node/nodeDebug.js",
        "runtime": "node",

        "languages": ["javascript", "typescript", "javascriptreact", "typescriptreact"],

        "configurationAttributes": {
          "launch": {
            "required": ["program"],
            "properties": {
              "program": {
                "type": "string",
                "description": "The program to debug."
              }
            }
          }
        },

        "initialConfigurations": [
          {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "${workspaceFolder}/app.js"
          }
        ],

        "configurationSnippets": [
          {
            "label": "Node.js: Attach Configuration",
            "description": "A new configuration for attaching to a running node program.",
            "body": {
              "type": "node",
              "request": "attach",
              "name": "${2:Attach to Port}",
              "port": 9229
            }
          }
        ],

        "variables": {
          "PickProcess": "extension.node-debug.pickNodeProcess"
        }
      }
    ]
  }
}
```

<br>

有关如何集成 debugger 的完整演练，请转到[Debugger Extension](https://code.visualstudio.com/api/extension-guides/debugger-extension)。

## contributes.grammars

为一种语言贡献一个 TextMate 语法。您必须提供此语法适用的 `language`、语法的 TextMate `scopeName` 和文件路径。

<br>

> 注意：包含语法的文件可以是 JSON（文件名以 .json 结尾）或 XML plist 格式（所有其他文件）。

<br>

```
{
  "contributes": {
    "grammars": [
      {
        "language": "markdown",
        "scopeName": "text.html.markdown",
        "path": "./syntaxes/markdown.tmLanguage.json",
        "embeddedLanguages": {
          "meta.embedded.block.frontmatter": "yaml"
        }
      }
    ]
  }
}
```

<br>

请参阅 [Syntax Highlight Guide](https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide) 以了解有关如何注册与语言关联的 TextMate 语法以接收语法高亮的更多信息。

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/grammars.png)

## contributes.iconThemes

为 VS Code 贡献一个文件图标主题。文件图标显示在文件名旁边，指示文件类型。 您必须指定一个 `id`（在设置中使用）、一个 `label` 和文件图标定义文件的路径。

<br>

```
{
  "contributes": {
    "iconThemes": [
      {
        "id": "my-cool-file-icons",
        "label": "Cool File Icons",
        "path": "./fileicons/cool-file-icon-theme.json"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/file-icon-themes.png)

<br>

有关如何创建文件图标主题的信息，请参阅[文件图标主题指南](https://code.visualstudio.com/api/extension-guides/file-icon-theme)。

## contributes.jsonValidation

为特定类型的 `json` 文件提供验证模式。`url` 值可以是扩展中包含的模式文件的本地路径，也可以是远程服务器 URL，例如 [json schema store](https://www.schemastore.org/json)。

<br>

```
{
  "contributes": {
    "jsonValidation": [
      {
        "fileMatch": ".jshintrc",
        "url": "https://json.schemastore.org/jshintrc"
      }
    ]
  }
}
```
<br>

## contributes.keybindings

提供一个键绑定规则，定义当用户按下组合键时应该调用什么命令。请参阅 [Key Bindings](https://code.visualstudio.com/docs/getstarted/keybindings) 主题，其中详细解释了键绑定。

<br>

提供键绑定将导致默认键盘快捷键显示您的规则，并且命令的每个 UI 表示现在都将显示您添加的键绑定。当然，当用户按下组合键时，将调用该命令。

<br>

> 注意：因为 VS Code 运行在 Windows、macOS 和 Linux 上，修饰符不同，你可以使用`“key”`来设置默认的组合键，并用特定的平台覆盖它。

<br>

> 注意：当调用命令时（从键绑定或命令面板），VS Code 将发出一个 `activationEvent` `onCommand:${command}`。 

<br>

```
{
  "contributes": {
    "keybindings": [
      {
        "command": "extension.sayHello",
        "key": "ctrl+f1",
        "mac": "cmd+f1",
        "when": "editorTextFocus"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/keybindings.png)

## contributes.languages

贡献编程语言的定义。这将引入一种新语言或丰富 VS Code 对一种语言的了解。

<br>

`concurrent.languages` 的主要作用是：

- 定义一个可以在 VS Code API 的其他部分重用的 `languageId`，例如 `vscode.TextDocument.getLanguageId()` 和 `onLanguage` Activation Events。
    - 您可以使用 `aliases` 字段提供人类可读的内容。列表中的第一项将用作人类可读的标签。
- 将文件扩展名、文件名模式、以特定行开头的文件（例如 hashbang）、mimetypes 与该 `languageId` 相关联。
- 为贡献的语言贡献一组[声明性语言特性](https://code.visualstudio.com/api/language-extensions/overview#declarative-language-features)。在[语言配置指南](https://code.visualstudio.com/api/language-extensions/language-configuration-guide)中了解有关可配置编辑功能的更多信息。
- 如果主题不包含该语言的图标，请提供一个可用作文件图标主题的图标

```
{
  "contributes": {
    "languages": [
      {
        "id": "python",
        "extensions": [".py"],
        "aliases": ["Python", "py"],
        "filenames": [],
        "firstLine": "^#!/.*\\bpython[0-9.-]*\\b",
        "configuration": "./language-configuration.json",
        "icon": {
          "light": "./icons/python-light.png",
          "dark": "./icons/python-dark.png"
        }
      }
    ]
  }
}
```

## contributes.menus

为编辑器或资源管理器提供命令的菜单项。菜单项定义包含选择时应调用的命令以及应显示该项的条件。后者是用 `when` 子句定义的，它使用键绑定 [when 子句上下文](https://code.visualstudio.com/api/references/when-clause-contexts)。

<br>

`command` 属性指示选择菜单项时要运行的命令。`submenu` 属性指示要在此位置呈现的子菜单。

<br>

声明 `command` 菜单项时，也可以使用 `alt` 属性定义替代命令。在打开菜单时按 ***Alt*** 会显示并调用它。在 Windows 和 Linux 上，***Shift*** 也这样做，这在 ***Alt*** 会触发窗口菜单栏的情况下很有用。

<br>

最后，`group` 属性定义了菜单项的排序和分组。`navigation` 组很特别，因为它总是被排序到菜单的顶部/开头。

<br>

> 请注意，`when` 子句适用于菜单，`enablement` 子句适用于命令。该 `enablement` 适用于所有菜单甚至键绑定，而 when 仅适用于单个菜单。

<br>

目前，可以为[以下内容](https://code.visualstudio.com/api/references/contribution-points#contributes.menus)设置 menu

<br>

> 注意：当从（上下文）菜单调用命令时，VS Code 会尝试推断当前选定的资源，并在调用命令时将其作为参数传递。例如，资源管理器中的菜单项传递所选资源的 URI，编辑器中的菜单项传递文档的 URI。

<br>

```
{
  "contributes": {
    "menus": {
      "editor/title": [
        {
          "when": "resourceLangId == markdown",
          "command": "markdown.showPreview",
          "alt": "markdown.showPreviewToSide",
          "group": "navigation"
        }
      ]
    }
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/menus.png)

<br>

这是一个子菜单菜单项：

<br>

```
{
  "contributes": {
    "menus": {
      "scm/title": [
        {
          "submenu": "git.commit",
          "group": "2_main@1",
          "when": "scmProvider == git"
        }
      ]
    }
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/submenu.png)

#### 命令面板菜单项的上下文特定可见性 

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。
