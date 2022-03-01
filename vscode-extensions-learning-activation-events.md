# VSCode 拓展激活事件

**Activation Events** 是您在 package.json [扩展清单](https://code.visualstudio.com/api/references/extension-manifest)的 `activationEvents` 字段中进行的一组 JSON 声明。当激活事件发生时，您的扩展程序将被激活。

<br>

以下是所有可用激活事件的列表：

- [`onLanguage`](https://code.visualstudio.com/api/references/activation-events#onLanguage) 每当打开解析为某种语言的文件时激活
- [`onCommand`](https://code.visualstudio.com/api/references/activation-events#onCommand) 每当调用命令时激活
- [`onDebug`](https://code.visualstudio.com/api/references/activation-events#onDebug) 调试会话开始之前被激活
- [`workspaceContains`](https://code.visualstudio.com/api/references/activation-events#workspaceContains) 每当打开一个文件夹并且该文件夹包含至少一个与 glob 模式匹配的文件时激活
- [`onFileSystem`](https://code.visualstudio.com/api/references/activation-events#onFileSystem) 每当读取来自特定方案的文件或文件夹时激活
- [`onView`](https://code.visualstudio.com/api/references/activation-events#onView) 在 VS Code 侧边栏中展开指定 id 的视图时激活
- [`onUri`](https://code.visualstudio.com/api/references/activation-events#onUri) 每当打开该扩展的系统范围 Uri 时激活
- [`onWebviewPanel`](https://code.visualstudio.com/api/references/activation-events#onWebviewPanel) 每当 VS Code 需要恢复具有匹配 `viewType` 的 [webview](https://code.visualstudio.com/api/extension-guides/webview) 时激活
- [`onCustomEditor`](https://code.visualstudio.com/api/references/activation-events#onCustomEditor) 每当 VS Code 需要创建具有匹配 `viewType` 的 [custom editor](https://code.visualstudio.com/api/extension-guides/custom-editors) 时激活
- [`onAuthenticationRequest`](https://code.visualstudio.com/api/references/activation-events#onAuthenticationRequest) 每当扩展请求具有匹配 `providerId` 的身份验证会话（通过 `authentication.getSession()` API）时激活
- [`onStartupFinished`](https://code.visualstudio.com/api/references/activation-events#onStartupFinished) 类似于 `*` 激活事件，但不会减慢 VS Code 的启动速度。目前，在所有 `*` 已激活的扩展程序都完成激活后会发出此事件
- [`*`](https://code.visualstudio.com/api/references/activation-events#Start-up) 每当 VS Code 启动时，会发出 `*` 激活事件

<br>

> [官网文档](https://code.visualstudio.com/api/references/activation-events)

## [onLanguage](https://code.visualstudio.com/api/references/activation-events#onLanguage)

每当打开解析为某种语言的文件时，就会发出此激活事件，并且将激活感兴趣的扩展。

<br>

```
...
"activationEvents": [
    "onLanguage:python"
]
...
```

<br>

onLanguage 事件采用[语言标识符](https://code.visualstudio.com/docs/languages/identifiers)的值。

<br>

可以在 `activationEvents` 数组中使用单独的 `onLanguage` 条目来声明多种语言。

<br>

```
"activationEvents": [
    "onLanguage:json",
    "onLanguage:markdown",
    "onLanguage:typescript"
]
...
```

## [onCommand](https://code.visualstudio.com/api/references/activation-events#onCommand)

每当调用命令时，就会发出此激活事件，并且将激活感兴趣的扩展：

<br>

```
...
"activationEvents": [
    "onCommand:extension.sayHello"
]
...
```

## [onDebug](https://code.visualstudio.com/api/references/activation-events#onDebug)

此激活事件被发出，感兴趣的扩展将在调试会话开始之前被激活：

<br>

```
...
"activationEvents": [
    "onDebug"
]
...
```

<br>

这是两个更细粒度的 `onDebug` 激活事件：

#### onDebugInitialConfigurations

`onDebugInitialConfigurations` 在调用 `DebugConfigurationProvider` 的 `provideDebugConfigurations` 方法之前被触发。

#### onDebugResolve

`onDebugResolve:type` 在调用指定类型的 `DebugConfigurationProvider` 的 `resolveDebugConfiguration` 方法之前触发。

<br>

> **经验法则**: 如果调试扩展的激活是轻量级的，使用 `onDebug`。如果是重量级，则根据 `DebugConfigurationProvider` 是否实现对应的方法 `provideDebugConfigurations` 和/或 `resolveDebugConfiguration` 使用 `onDebugInitialConfigurations` 和/或 `onDebugResolve`。有关这些方法的更多详细信息，请参阅[使用 DebugConfigurationProvider](https://code.visualstudio.com/api/extension-guides/debugger-extension#using-a-debugconfigurationprovider)。

## [workspaceContains](https://code.visualstudio.com/api/references/activation-events#workspaceContains)

每当打开一个文件夹并且该文件夹包含至少一个与 glob 模式匹配的文件时，就会发出此激活事件并且感兴趣的扩展将被激活。

<br>

```
...
"activationEvents": [
    "workspaceContains:**/.editorconfig"
]
...
```

## [onFileSystem](https://code.visualstudio.com/api/references/activation-events#onFileSystem)

每当读取来自特定方案的文件或文件夹时，都会发出此激活事件，并且将激活感兴趣的扩展。这通常是 `file-scheme`，但使用自定义文件系统提供程序会出现更多方案，例如 `ftp` 或 `ssh`。

<br>

```
...
"activationEvents": [
    "onFileSystem:sftp"
]
...
```

## [onView](https://code.visualstudio.com/api/references/activation-events#onView)

只要在 VS Code 侧边栏中展开指定 id 的视图（扩展或源代码控制是内置视图的示例），就会发出此激活事件并且感兴趣的扩展将被激活。

<br>

只要具有 `nodeDependencies` id 的视图可见，下面的激活事件就会触发：

<br>

...
"activationEvents": [
    "onView:nodeDependencies"
]
...

## [onUri](https://code.visualstudio.com/api/references/activation-events#onUri)

每当打开该扩展的系统范围 Uri 时，就会发出此激活事件，并且将激活感兴趣的扩展。Uri 方案固定为 `vscode` 或 `vscode-insiders`。 Uri 权限必须是扩展的标识符。 Uri 的其余部分是任意的。

<br>

```
...
"activationEvents": [
    "onUri"
]
...
```

<br>

如果 `vscode.git` 扩展将 `onUri` 定义为激活事件，它将在以下任一 Uris 都打开时被激活：

- `vscode://vscode.git/init`
- `vscode://vscode.git/clone?url=https%3A%2F%2Fgithub.com%2FMicrosoft%2Fvscode-vsce.git`
- `vscode-insiders://vscode.git/init` (for VS Code Insiders)

## [onWebviewPanel](https://code.visualstudio.com/api/references/activation-events#onWebviewPanel)

每当 VS Code 需要恢复具有匹配 `viewType` 的 [webview](https://code.visualstudio.com/api/extension-guides/webview) 时，就会发出此激活事件并激活感兴趣的扩展。

<br>

比如下面的 onWebviewPanel 的声明：

<br>

```
"activationEvents": [
    "onWebviewPanel:catCoding"
]
```

<br>

当 VS Code 需要使用 `viewType: catCoding` 恢复 webview 时，将导致激活扩展。viewType 在对 `window.createWebviewPanel` 的调用中设置，您将需要另一个激活事件（例如，onCommand）来初始激活您的扩展并创建 webview。

## [onCustomEditor](https://code.visualstudio.com/api/references/activation-events#onCustomEditor)

每当 VS Code 需要创建具有匹配 `viewType` 的 [custom editor](https://code.visualstudio.com/api/extension-guides/custom-editors) 时，就会发出此激活事件并激活感兴趣的扩展。

<br>

比如下面的 `onCustomEditor` 的声明：

<br>

```
"activationEvents": [
    "onCustomEditor:catCustoms.pawDraw"
]
```

<br>

当 VS Code 需要使用 `viewType: catCustoms.pawDraw` 恢复自定义编辑器时，将导致激活扩展。`viewType` 在 [`customEditors` 贡献点](https://code.visualstudio.com/api/extension-guides/custom-editors#contribution-point)中设置，并通过 `registerCustomEditorProvider` 绑定到提供程序。

## [onAuthenticationRequest](https://code.visualstudio.com/api/references/activation-events#onAuthenticationRequest)

每当扩展请求具有匹配 `providerId` 的身份验证会话（通过 `authentication.getSession()` API）时，就会发出此激活事件，并且感兴趣的扩展将被激活。

<br>

例如下面的 `onAuthenticationRequest` 的声明：

<br>

```
"activationEvents": [
    "onAuthenticationRequest:github"
]
```

<br>

当 VS Code 需要检索 `github` 类型的 `AuthenticationSession` 时，将导致激活扩展。

## [onStartupFinished](https://code.visualstudio.com/api/references/activation-events#onStartupFinished)

这个激活事件被触发，感兴趣的扩展将在 VS Code 启动后的**一段时间内**被激活。这类似于 `*` 激活事件，但不会减慢 VS Code 的启动速度。目前，在所有 `*` 已激活的扩展程序都完成激活后会发出此事件。

<br>

```
...
"activationEvents": [
    "onStartupFinished"
]
...
```

## [Start up](https://code.visualstudio.com/api/references/activation-events#Start-up)

每当 VS Code 启动时，会发出 `*` 激活事件，感兴趣的扩展将被激活。

<br>

> 注意：为确保良好的用户体验，请仅当您的用例中没有其他激活事件组合有效时，才在您的扩展程序中使用此激活事件。

<br>

```
...
"activationEvents": [
    "*"
]
...
```

<br>

> 注意：一个扩展可以监听多个激活事件，这比监听 `"*"` 更好。

<br>

> 注意：扩展必须从其主模块中导出一个 `activate()` 函数，并且当发出任何指定的激活事件时，VS Code 只会**调用它一次**。此外，扩展应从其主模块导出 `deactivate()` 函数，以在 VS Code 关闭时执行清理任务。如果清理过程是异步的，扩展程序必须从 `deactivate()` 返回一个 `Promise`。如果清理同步运行，扩展可能会从 `deactivate()` 返回 `undefined`。

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到[此处](https://juejin.cn/post/7067825724773629989/)。