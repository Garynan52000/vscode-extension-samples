# VSCode 拓展清单中的贡献点

**Contribution Points** - 是您在 `package.json` [扩展清单](https://code.visualstudio.com/api/references/extension-manifest)的贡献字段中进行的一组 JSON 声明。您的扩展注册贡献点以扩展 Visual Studio Code 中的各种功能。

<br>

包括：
- [contributes.breakpoints](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.breakpoints)：列出拓展中将急用设置断点的语言文件类型。
- [contributes.colors](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.colors)：提供新的主题颜色。
- [contributes.commands](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.commands)：注册命令并为其再编辑器中提供 UI，命令默认会显示在**Command Palette** (`Ctrl+Shift+P`)。
- [contributes.configuration](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.configuration)：列出拓展中需要使用到的配置项。
- [contributes.configurationDefaults](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.configurationDefaults)：提供默认的特定于语言的编辑器配置。这将覆盖所提供语言的默认编辑器配置。
- [contributes.customEditors](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.customEditors)：定义自定义编辑器。
- [contributes.debuggers](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.debuggers)：为 VS Code 贡献一个调试器。
- [contributes.grammars](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.grammars)：为一种语言贡献一个 TextMate 语法。
- [contributes.iconThemes](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.iconThemes)：为 VS Code 贡献一个文件图标主题。
- [contributes.jsonValidation](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.jsonValidation)：为特定类型的 json 文件提供验证模式。
- [contributes.keybindings](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.keybindings)：提供一个按键键绑定规则。
- [contributes.languages](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.languages)：贡献编程语言的定义。
- [contributes.menus](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.menus)：为编辑器或资源管理器提供命令的菜单项。
- [contributes.problemMatchers](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.problemMatchers)：贡献问题匹配器。
- [contributes.problemPatterns](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.problemPatterns)：贡献可以在问题匹配器中使用的命名问题模式。
- [contributes.productIconThemes](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.productIconThemes)：为 VS Code 贡献一个产品图标主题。产品图标是 VS Code 中使用的所有图标，除了文件图标和扩展提供的图标。
- [contributes.resourceLabelFormatters](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.resourceLabelFormatters)：提供资源标签格式化程序，指定如何在工作台中的任何位置显示 URI。
- [contributes.snippets](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.snippets)：为特定语言贡献代码片段。
- [contributes.submenus](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.submenus)：贡献一个子菜单作为可以贡献菜单项的占位符。
- [contributes.taskDefinitions](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.taskDefinitions)：定义任务。
- [contributes.themes](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.themes)：为 VS Code 提供颜色主题，在编辑器中为语法标记定义工作台颜色和样式。
- [contributes.typescriptServerPlugins](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.typescriptServerPlugins)：提供增强 VS Code 的 JavaScript 和 TypeScript 支持的 [TypeScript server plugins](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fmicrosoft%2FTypeScript%2Fwiki%2FWriting-a-Language-Service-Plugin)。
- [contributes.views](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.views)：为 VS Code 贡献一个视图。
- [contributes.viewsContainers](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.viewsContainers)：贡献一个可以贡献 [Custom views](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.views) 的视图容器。
- [contributes.viewsWelcome](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.viewsWelcome)：为 [Custom views](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.views) 贡献欢迎内容。
- [contributes.walkthroughs](https://link.juejin.cn/?target=https%3A%2F%2Fcode.visualstudio.com%2Fapi%2Freferences%2Fcontribution-points%23contributes.walkthroughs)：贡献演示以显示在 Getting Started page。演示会在安装扩展程序时自动打开，并提供一种方便的方式向用户介绍扩展程序的功能。

<br>

> [官网文档](https://code.visualstudio.com/api/references/contribution-points#contributes.breakpoints)

## [contributes.breakpoints](https://code.visualstudio.com/api/references/contribution-points#contributes.breakpoints)

通常调试器扩展也会有一个 `contributors.breakpoints` 条目，其中扩展列出了将启用设置断点的语言文件类型。

<br>

```
{
  "contributes": {
    "breakpoints": [
      {
        "language": "javascript"
      },
      {
        "language": "javascriptreact"
      }
    ]
  }
}
```

## [contributes.colors](https://code.visualstudio.com/api/references/contribution-points#contributes.colors)

提供新的主题颜色。这些颜色可以被编辑器装饰器和状态栏中的扩展使用。一旦定义，用户可以在 `workspace.colorCustomization` 设置中自定义颜色，用户主题可以设置颜色值。

<br>

```
{
  "contributes": {
    "colors": [
      {
        "id": "superstatus.error",
        "description": "Color for error message in the status bar.",
        "defaults": {
          "dark": "errorForeground",
          "light": "errorForeground",
          "highContrast": "#010203"
        }
      }
    ]
  }
}
```

<br>

可以为颜色默认值定义浅色、深色和高对比度的主题颜色，并且可以是对现有颜色的引用或[颜色十六进制值](https://code.visualstudio.com/api/references/theme-color#color-formats)。

<br>

扩展可以使用 `ThemeColor` API 使用新的和现有的主题颜色：

<br>

```
const errorColor = new vscode.ThemeColor('superstatus.error');
```

## [contributes.commands](https://code.visualstudio.com/api/references/contribution-points#contributes.commands)

为包含标题和（可选）图标、类别和启用状态的命令提供 UI。启用用 `when` 子句表示。默认情况下，命令显示在**Command Palette** (`Ctrl+Shift+P`)，但它们也可以显示在[其他菜单](https://code.visualstudio.com/api/references/contribution-points#contributes.menus)中

<br>

贡献命令的呈现取决于包含的菜单。例如，**Command Palette**会在命令前面加上它们的 `category`，允许轻松分组。但是，**Command Palette**既不显示图标也不禁用命令。另一方面，编辑器上下文菜单显示禁用的项目，但不显示类别标签。

<br>

> 注意：当调用命令时（从键绑定、命令面板、任何其他菜单或以编程方式），VS Code 将发出一个 [activationEvent `onCommand:${command}`](https://code.visualstudio.com/api/references/activation-events#onCommand)。

<br>

> 注意：使用 [product icons](https://code.visualstudio.com/api/references/icons-in-labels#icon-listing) 中的图标时，设置 `light` 和 `dark` 将禁用图标。正确的语法是 `"icon": "$(book)"`

<br>

```
{
  "contributes": {
    "commands": [
      {
        "command": "extension.sayHello",
        "title": "Hello World",
        "category": "Hello",
        "icon": {
          "light": "path/to/light/icon.svg",
          "dark": "path/to/dark/icon.svg"
        }
      }
    ]
  }
}
```

<br>

请参阅[命令扩展指南](https://code.visualstudio.com/api/extension-guides/command)以了解有关在 VS Code 扩展中使用命令的更多信息。

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/commands.png)

#### Command 图标的格式

- 尺寸: 图标应为 16x16，内边距为 1 像素（图像为 14x14）并居中
- 颜色: 图标应使用单一颜色。
- 格式: 尽管接受任何图像文件类型，但建议使用 SVG 图标。

![image](https://code.visualstudio.com/assets/api/references/contribution-points/command-icons.png)

## [contributes.configuration](https://code.visualstudio.com/api/references/contribution-points#contributes.configuration)

贡献的配置密钥是向用户公开的。通过使用设置编辑器或直接编辑 JSON 设置文件，用户将能够将这些配置选项设置为用户设置或工作区设置。

<br>

此部分可以是单个对象，表示单个设置类别，也可以是对象数组，表示多个设置类别。如果有多个类别的设置，设置编辑器将在该扩展的目录中显示一个子菜单，并且标题键将用于子菜单条目名称

<br>

```
{
  "contributes": {
    "configuration": {
      "title": "TypeScript",
      "properties": {
        "typescript.useCodeSnippetsOnMethodSuggest": {
          "type": "boolean",
          "default": false,
          "description": "Complete functions with their parameter signature."
        },
        "typescript.tsdk": {
          "type": ["string", "null"],
          "default": null,
          "description": "Specifies the folder path containing the tsserver and lib*.d.ts files to use."
        }
      }
    }
  }
}
```

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

## [contributes.configurationDefaults](https://code.visualstudio.com/api/references/contribution-points#contributes.configurationDefaults)

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

## [contributes.customEditors](https://code.visualstudio.com/api/references/contribution-points#contributes.customEditors)

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

## [contributes.debuggers](https://code.visualstudio.com/api/references/contribution-points#contributes.debuggers)

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

有关如何集成 debugger 的完整演示，请转到[Debugger Extension](https://code.visualstudio.com/api/extension-guides/debugger-extension)。

## [contributes.grammars](https://code.visualstudio.com/api/references/contribution-points#contributes.grammars)

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

## [contributes.iconThemes](https://code.visualstudio.com/api/references/contribution-points#contributes.iconThemes)

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

## [contributes.jsonValidation](https://code.visualstudio.com/api/references/contribution-points#contributes.jsonValidation)

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

## [contributes.keybindings](https://code.visualstudio.com/api/references/contribution-points#contributes.keybindings)

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

## [contributes.languages](https://code.visualstudio.com/api/references/contribution-points#contributes.languages)

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

## [contributes.menus](https://code.visualstudio.com/api/references/contribution-points#contributes.menus)

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

这是一个命令菜单项：

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

在 `package.json` 中注册命令时，它们将自动显示在命令面板中 (Command Palette 按 **Ctrl+Shift+P**)。为了更好地控制命令可见性，有 `commandPalette` 菜单项。它允许您定义一个 `when` 条件来控制命令是否应该在命令面板中可见。

<br>

当在编辑器中有选中的内容时，下面的代码片段使“Hello World”命令仅在命令面板中可见：

<br>

```
{
  "commands": [
    {
      "command": "extension.sayHello",
      "title": "Hello World"
    }
  ],
  "menus": {
    "commandPalette": [
      {
        "command": "extension.sayHello",
        "when": "editorHasSelection"
      }
    ]
  }
}
```

#### 分组排序

菜单项可以被排列到分组里。它们使用以下默认值/规则按字典顺序排序。您可以将菜单项添加到这些组中，或者在其间、下方或上方添加新的菜单项组。

<br>

**编辑器上下文** 菜单具有以下默认组：

- `navigation` - 在所有情况下，导航组都排在第一位。
- `1_modification` - 接下来是该组，包含修改代码的命令。
- `9_cutcopypaste` - 具有基本编辑命令的倒数第二个默认组。
- `z_commands` - 最后一个默认组，其中包含打开命令面板的条目。

![image](https://code.visualstudio.com/assets/api/references/contribution-points/groupSorting.png)

<br>

**资源管理器上下文** 菜单具有以下默认组：

- `navigation` - 这个组在所有情况下都排在第一位。
- `2_workspace` - 与工作区操作相关的命令
- `3_compare` - 与在差异编辑器中比较文件相关的命令。
- `4_search` - 与搜索视图中的搜索相关的命令。
- `5_cutcopypaste` - 与剪切、复制和粘贴文件相关的命令。
- `6_copypath` - 与复制文件路径相关的命令。
- `7_modification` - 与文件修改相关的命令。

<br>

**编辑器选项卡上下文** 菜单具有以下默认组：

- `1_close` - 与关闭编辑器相关的命令。
- `3_preview` - 与固定编辑器相关的命令。

<br>

**编辑器标题** 菜单具有以下默认组：

- `navigation` - 与导航相关的命令。
- `1_run` - 与运行和调试编辑器相关的命令。
- `1_diff` - 与使用差异编辑器相关的命令。
- `3_open` - 与打开编辑器相关的命令。
- `5_close` - 与关闭编辑器相关的命令。

`navigation` 和 `1_run` 显示在主编辑器标题区域中。其他组显示在次要区域 - `...` 菜单下。

<br>

**时间轴视图项上下文** 菜单具有以下默认组：

- `inline` - 重要或经常使用的时间线项目命令。呈现为工具栏。
- `1_actions` - 与使用时间线项目相关的命令。
- `5_copy` - 与复制时间线项目信息相关的命令。

<br>

**扩展视图上下文** 菜单具有以下默认组：

- `1_copy` - 与复制扩展信息相关的命令。 
- `2_configure` - 与配置扩展相关的命令。

#### 在组内排序

组内的顺序取决于标题或顺序属性。通过将 `@<number>` 附加到组标识符来指定菜单项的组本地顺序，如下所示：

<br>

```
{
  "editor/title": [
    {
      "when": "editorHasSelection",
      "command": "extension.Command",
      "group": "myGroup@1"
    }
  ]
}
```

## [contributes.problemMatchers](https://code.visualstudio.com/api/references/contribution-points#contributes.problemMatchers)

贡献问题匹配器模式。这些贡献在输出面板运行器和终端运行器中都起作用。下面是一个在扩展中为 gcc 编译器提供问题匹配器的示例：

<br>

```
{
  "contributes": {
    "problemMatchers": [
      {
        "name": "gcc",
        "owner": "cpp",
        "fileLocation": ["relative", "${workspaceFolder}"],
        "pattern": {
          "regexp": "^(.*):(\\d+):(\\d+):\\s+(warning|error):\\s+(.*)$",
          "file": 1,
          "line": 2,
          "column": 3,
          "severity": 4,
          "message": 5
        }
      }
    ]
  }
}
```

<br>

这个问题匹配器现在可以通过名称引用 `$gcc` 在 `tasks.json` 文件中使用。一个示例如下所示

<br>

```
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build",
      "command": "gcc",
      "args": ["-Wall", "helloWorld.c", "-o", "helloWorld"],
      "problemMatcher": "$gcc"
    }
  ]
}
```

<br>

Also see: [Defining a Problem Matcher](https://code.visualstudio.com/docs/editor/tasks#_defining-a-problem-matcher)

## [contributes.problemPatterns](https://code.visualstudio.com/api/references/contribution-points#contributes.problemPatterns)

贡献可以在问题匹配器中使用的命名问题模式（见上文）

## [contributes.productIconThemes](https://code.visualstudio.com/api/references/contribution-points#contributes.productIconThemes)

为 VS Code 贡献一个产品图标主题。产品图标是 VS Code 中使用的所有图标，除了文件图标和扩展提供的图标。

<br>

您必须指定 id（在设置中使用）、标签和图标定义文件的路径。

<br>

```
{
  "contributes": {
    "productIconThemes": [
      {
        "id": "elegant",
        "label": "Elegant Icon Theme",
        "path": "./producticons/elegant-product-icon-theme.json"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/product-icon-themes.png)

<br>

See the [Product Icon Theme Guide](https://code.visualstudio.com/api/extension-guides/product-icon-theme) on how to create a Product Icon Theme.

## [contributes.resourceLabelFormatters](https://code.visualstudio.com/api/references/contribution-points#contributes.resourceLabelFormatters)

提供资源标签格式化程序，指定如何在工作台中的任何位置显示 URI。例如，扩展如何使用方案 `remotehub` 为 URI 提供格式化程序：

<br>

```
{
  "contributes": {
    "resourceLabelFormatters": [
      {
        "scheme": "remotehub",
        "formatting": {
          "label": "${path}",
          "separator": "/",
          "workspaceSuffix": "GitHub"
        }
      }
    ]
  }
}
```

<br>

这意味着所有具有 scheme 为 `remotehub` 的 URI 都将通过仅显示 URI 的路径段来呈现，分隔符将是 `/`。具有 `remotehub` URI 的工作区将在其标签中具有 `GitHub` 后缀。

## [contributes.snippets](https://code.visualstudio.com/api/references/contribution-points#contributes.snippets)

为特定语言贡献代码片段。`language` 属性是[语言标识符](https://code.visualstudio.com/docs/languages/identifiers)，`path` 是片段文件的相对路径，它以 [VS Code 片段格式](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_snippet-syntax)定义片段。

<br>

下面的示例显示了为 Go 语言添加片段。

<br>

```
{
  "contributes": {
    "snippets": [
      {
        "language": "go",
        "path": "./snippets/go.json"
      }
    ]
  }
}
```

## [contributes.submenus](https://code.visualstudio.com/api/references/contribution-points#contributes.submenus)

贡献一个子菜单作为可以贡献菜单项的占位符。子菜单需要在父菜单中显示 `label`。

<br>

除了标题之外，命令还可以定义 VS Code 将在编辑器标题菜单栏中显示的图标。

<br>

```
{
  "contributes": {
    "submenus": [
      {
        "id": "git.commit",
        "label": "Commit"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/submenucontrib.png)

## [contributes.taskDefinitions](https://code.visualstudio.com/api/references/contribution-points#contributes.taskDefinitions)

贡献并定义一个对象迭代结构，允许唯一地标识系统中的贡献任务。任务定义至少有一个 `type` 属性，但它通常定义附加属性。例如，在 `package.json` 文件中表示脚本的任务的任务定义如下所示：

<br>

```
{
  "taskDefinitions": [
    {
      "type": "npm",
      "required": ["script"],
      "properties": {
        "script": {
          "type": "string",
          "description": "The script to execute"
        },
        "path": {
          "type": "string",
          "description": "The path to the package.json file. If omitted the package.json in the root of the workspace folder is used."
        }
      }
    }
  ]
}
```

<br>

任务定义是使用 JSON 模式语法为 `required` 和 `properties` 属性定义的。`type` 属性定义任务类型。如果上面的例子：

- `"type": "npm"` 将任务定义与 npm 任务相关联
- `"required": [ "script" ]` 将 `script` 属性定义为强制。 `path` 属性是可选的。
- `"properties" : { ... }` 定义附加属性及其类型。

当扩展实际创建一个任务时，它需要传递一个符合 `package.json` 文件中贡献的任务定义的 `TaskDefinition`。在 `package.json` 文件中为测试脚本创建任务的 `npm` 示例如下所示：

<br>

```
let task = new vscode.Task({ type: 'npm', script: 'test' }, ....);
```

## [contributes.themes](https://code.visualstudio.com/api/references/contribution-points#contributes.themes)

为 VS Code 提供颜色主题，在编辑器中为语法标记定义工作台颜色和样式。

<br>

您必须指定 `label`，主题是 **深色主题** 还是 **浅色主题** （以便 VS Code 的其余部分更改以匹配您的主题）和文件路径（JSON 格式）

<br>

```
{
  "contributes": {
    "themes": [
      {
        "label": "Monokai",
        "uiTheme": "vs-dark",
        "path": "./themes/monokai-color-theme.json"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/color-themes.png)

<br>

See the [Color Theme Guide](https://code.visualstudio.com/api/extension-guides/color-theme) on how to create a Color Theme.

## [contributes.typescriptServerPlugins](https://code.visualstudio.com/api/references/contribution-points#contributes.typescriptServerPlugins)

提供增强 VS Code 的 JavaScript 和 TypeScript 支持的 [TypeScript server plugins](https://github.com/microsoft/TypeScript/wiki/Writing-a-Language-Service-Plugin)：

<br>

```
{
  "contributes": {
    "typescriptServerPlugins": [
      {
        "name": "typescript-styled-plugin"
      }
    ]
  }
}
```

<br>

上面的示例扩展提供了 `typescript-styled-plugin`，它为 JavaScript 和 TypeScript 添加了样式化组件 IntelliSense。此插件将从扩展加载，并且必须作为扩展中的正常 NPM `dependency` 安装：

<br>

```
{
  "dependencies": {
    "typescript-styled-plugin": "*"
  }
}
```

<br>

当用户使用 VS Code 的 TypeScript 版本时，会为所有 JavaScript 和 TypeScript 文件加载 TypeScript 服务器插件。如果用户使用的是工作区版本的 TypeScript，它们不会被激活，除非插件明确设置 `"enableForWorkspaceTypeScriptVersions": true`。

<br>

```
{
  "contributes": {
    "typescriptServerPlugins": [
      {
        "name": "typescript-styled-plugin",
        "enableForWorkspaceTypeScriptVersions": true
      }
    ]
  }
}
```

#### 插件配置

扩展可以通过 VS Code 的内置 TypeScript 扩展提供的 API 将配置数据发送到贡献的 TypeScript 插件：

<br>

```
// In your VS Code extension

export async function activate(context: vscode.ExtensionContext) {
  // Get the TS extension
  const tsExtension = vscode.extensions.getExtension('vscode.typescript-language-features');
  if (!tsExtension) {
    return;
  }

  await tsExtension.activate();

  // Get the API from the TS extension
  if (!tsExtension.exports || !tsExtension.exports.getAPI) {
    return;
  }

  const api = tsExtension.exports.getAPI(0);
  if (!api) {
    return;
  }

  // Configure the 'my-typescript-plugin-id' plugin
  api.configurePlugin('my-typescript-plugin-id', {
    someValue: process.env['SOME_VALUE']
  });
}
```

<br>

TypeScript 服务器插件通过 `onConfigurationChanged` 方法接收配置数据：

<br>

```
// In your TypeScript plugin

import * as ts_module from 'typescript/lib/tsserverlibrary';

export = function init({ typescript }: { typescript: typeof ts_module }) {
  return {
    create(info: ts.server.PluginCreateInfo) {
      // Create new language service
    },
    onConfigurationChanged(config: any) {
      // Receive configuration changes sent from VS Code
    }
  };
};
```

<br>

此 API 允许 VS Code 扩展将 VS Code 设置与 TypeScript 服务器插件同步，或动态更改插件的行为。查看 [TypeScript TSLint 插件](https://github.com/microsoft/vscode-typescript-tslint-plugin/blob/main/src/index.ts)和 [lit-html](https://github.com/mjbvz/vscode-lit-html/blob/master/src/index.ts) 扩展，了解如何在实践中使用此 API。

## [contributes.views](https://code.visualstudio.com/api/references/contribution-points#contributes.views)

为 VS Code 贡献一个视图。您必须为视图指定标识符和名称。您可以为以下视图容器做出贡献：

- `explorer`: Activity Bar 中的资源管理器视图容器
- `scm`: Activity Bar 中的源代码控制管理 (SCM) 视图容器
- `debug`: Activity Bar 中的运行和调试视图容器
- `test`: Activity Bar 中的测试视图容器
- `Custom` 由扩展提供的 [Custom view containers](https://code.visualstudio.com/api/references/contribution-points#contributes.viewsContainers)

当用户打开视图时，VS Code 将发出一个 `activationEvent` `onView:${viewId}` （以下示例的 `onView:nodeDependencies`）。您还可以通过提供 `when` 上下文值来控制视图的可见性。当无法显示标题时（例如，当视图被拖到活动栏时）将使用指定的 `icon`。当视图移出其默认视图容器并需要额外的上下文时，将使用 `contextualTitle`。

<br>

```
{
  "contributes": {
    "views": {
      "explorer": [
        {
          "id": "nodeDependencies",
          "name": "Node Dependencies",
          "when": "workspaceHasPackageJSON",
          "icon": "media/dep.svg",
          "contextualTitle": "Package Explorer"
        }
      ]
    }
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/views.png)

<br>

可以通过两种方式填充视图的内容：

- 使用 [TreeView](https://code.visualstudio.com/api/references/vscode-api#TreeView) 通过 `createTreeView` API 提供 [data provider](https://code.visualstudio.com/api/references/vscode-api#TreeDataProvider) 或直接通过 `registerTreeDataProvider` API 注册数据提供者来填充数据。TreeViews 非常适合显示分层数据和列表。请参阅 [tree-view-sample](https://github.com/microsoft/vscode-extension-samples/tree/main/tree-view-sample)。
- 通过向 `registerWebviewViewProvider` 注册 [provider](https://code.visualstudio.com/api/references/vscode-api#WebviewViewProvider) 来使用 [WebviewView](https://code.visualstudio.com/api/references/vscode-api#WebviewView)。Webview 视图允许在视图中呈现任意 HTML。有关更多详细信息，请参阅 [webview view sample extension](https://github.com/microsoft/vscode-extension-samples/tree/main/webview-view-sample)。

## [contributes.viewsContainers](https://code.visualstudio.com/api/references/contribution-points#contributes.viewsContainers)

贡献一个可以贡献 [Custom views](https://code.visualstudio.com/api/references/contribution-points#contributes.views) 的视图容器。您必须为视图容器指定标识符、标题和图标。目前，您可以将它们贡献给Activity Bar（`activitybar`）和Panel（`panel`）。下面的示例显示了 `Package Explorer` 视图容器是如何贡献给 Activity Bar 的，以及视图是如何贡献给它的。

<br>

```
{
  "contributes": {
    "viewsContainers": {
      "activitybar": [
        {
          "id": "package-explorer",
          "title": "Package Explorer",
          "icon": "resources/package-explorer.svg"
        }
      ]
    },
    "views": {
      "package-explorer": [
        {
          "id": "package-dependencies",
          "name": "Dependencies"
        },
        {
          "id": "package-outline",
          "name": "Outline"
        }
      ]
    }
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/custom-views-container.png)

<br>

#### 图标规格

- **Size**: 图标应为 24x24 并居中。
- **Color**: 颜色：图标应使用单一颜色。
- **Format**: 尽管接受任何图像文件类型，但建议使用 SVG 图标。
- **States**: 所有图标都继承以下状态样式：

<table>
  <tr>
    <th>State</th><th>Opacity</th>
  </tr>
  <tr>
    <td>Default</td><td>60%</td>
  </tr>
  <tr>
    <td>Hover</td><td>100%</td>
  </tr>
  <tr>
    <td>Active</td><td>100%</td>
  </tr>
</table>

## [contributes.viewsWelcome](https://code.visualstudio.com/api/references/contribution-points#contributes.viewsWelcome)

为 [Custom views](https://code.visualstudio.com/api/references/contribution-points#contributes.views) 贡献欢迎内容。欢迎内容仅适用于空树视图。如果树没有孩子，则视图被认为是空的。按照惯例，任何单独位于一行的命令链接都显示为按钮。您可以使用 `view` 属性指定欢迎内容应用到的视图。欢迎内容的可见性可以通过 `when` 上下文值来控制。显示为欢迎内容的文本由 `contents` 属性设置。

<br>

```
{
  "contributes": {
    "viewsWelcome": [
      {
        "view": "scm",
        "contents": "In order to use git features, you can open a folder containing a git repository or clone from a URL.\n[Open Folder](command:vscode.openFolder)\n[Clone Repository](command:git.clone)\nTo learn more about how to use git and source control in VS Code [read our docs](https://aka.ms/vscode-scm).",
        "when": "config.git.enabled && git.state == initialized && workbenchState == empty"
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/viewsWelcome.png)

<br>

多个欢迎内容项目可以贡献给一个视图。发生这种情况时，来自 VS Code 核心的内容首先出现，然后是来自内置扩展的内容，然后是来自所有其他扩展的内容。

## [contributes.walkthroughs](https://code.visualstudio.com/api/references/contribution-points#contributes.walkthroughs)

[Sample extension](https://github.com/microsoft/vscode-extension-samples/tree/main/getting-started-sample)

<br>

贡献演示以显示在 **Getting Started page**。演示会在安装扩展程序时自动打开，并提供一种方便的方式向用户介绍扩展程序的功能。

<br>

演示由标题、描述、ID 和一系列步骤组成。此外，可以使用 `when` 条件基于上下文键将演示设置为隐藏或显示。例如，解释 Linux 平台上的设置的演示可以在以下情况下给出 `when: "isLinux"` 仅出现在 Linux 机器上

<br>

演示中的每个步骤都有一个标题、描述、id 和媒体元素（图像或 Markdown 内容），以及将导致检查该步骤的一组可选事件（如下例所示）。步 `description` 述为 Markdown 内容，支持 `**bold**` 表示加粗、`__underlined__` 表示下划线、```code``` 表示代码的渲染，以及链接。与演示类似，可以根据上下文键在隐藏或显示条件时给出步骤。

<br>

```
{
  "contributes": {
    "walkthroughs": [
      {
        "id": "sample",
        "title": "Sample",
        "description": "A sample walkthrough",
        "steps": [
          {
            "id": "runcommand",
            "title": "Run Command",
            "description": "This step will run a command and check off once it has been run.\n[Run Command](command:getting-started-sample.runCommand)",
            "media": { "image": "media/image.png", "altText": "Empty image" },
            "completionEvents": ["onCommand:getting-started-sample.runCommand"]
          },
          {
            "id": "changesetting",
            "title": "Change Setting",
            "description": "This step will change a setting and check off when the setting has changed\n[Change Setting](command:getting-started-sample.changeSetting)",
            "media": { "markdown": "media/markdown.md" },
            "completionEvents": ["onSettingChanged:getting-started-sample.sampleSetting"]
          }
        ]
      }
    ]
  }
}
```

<br>

![image](https://code.visualstudio.com/assets/api/references/contribution-points/walkthroughs.png)

#### Completion events

默认情况下，如果没有提供 `completionEvents` 事件，则当单击它的任何按钮时将检查该步骤，或者如果该步骤没有按钮，则在打开它时检查该步骤。如果需要更精细的控制，可以提供 `completionEvents` 事件列表。

<br>

可用的完成事件包括：

- `onCommand:myCommand.id`: 运行命令时检查步骤。
- `onSettingChanged:mySetting.id`: 修改给定设置后，请检查关闭步骤。
- `onContext:contextKeyExpression`: 当上下文键表达式评估为真时，检查关闭步骤。
- `extensionInstalled:myExt.id`: 如果安装了给定的扩展程序，请检查步骤。
- `onView:myView.id`: 一旦给定视图变得可见，请检查关闭步骤。
- `onLink:https://...`: 通过演示打开给定链接后，请检查步骤。

一旦一个步骤被选中，它将保持选中状态，直到用户明确取消选中该步骤或重置其进度（通过 **Getting Started: Reset Progress** 命令）。

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。
