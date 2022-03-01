# VSCode 拓展程序学习线路

VSCode 拓展程序学习线路，帮助引导学习方向。本文主要内容包括快速起步以及增强能力清单。后续会持续更新更多的学习内容。

<br>

> [官方文档](https://code.visualstudio.com/api)

## 快速起步

#### 安装命令行脚手架工具

```
npm install -g yo generator-code
```

#### 运行命令创建拓展程序项目

```
yo code

# ? What type of extension do you want to create? New Extension (TypeScript)
# ? What's the name of your extension? HelloWorld
### Press <Enter> to choose default for all options below ###

# ? What's the identifier of your extension? helloworld
# ? What's the description of your extension? LEAVE BLANK
# ? Initialize a git repository? Yes
# ? Bundle the source code with webpack? No
# ? Which package manager to use? npm

# ? Do you want to open the new folder with Visual Studio Code? Open with `code`
```

<br>

根据提示选择你想创建的项目类型和相关功能选项。

#### 使用 VSCode 编辑器来开发拓展程序

- 下载最新版本的 [VSCode](https://code.visualstudio.com/)
- 开发前确保 VSCode 更新到最新版本
- 打开 VSCode ，并打开项目的文件夹。可以通过在命令行中运行 `code [path to your project]` 来打开项目，如：`code ./example-extension`
- 按下 `F5` 按键即可启动项目
- 更改项目代码之后可以重新运行项目，或者在 VSCode 中 按下 `ctrl + shift + p` 运行编辑器命令 **Developer: Reload Window**，即可看到新内容。
- **Debugger** 调试就和平时用 VSCode 调试 Node.js 一样，有需要可以参考 [Node.js Debugging Topic](https://code.visualstudio.com/docs/nodejs/nodejs-debugging)

#### VSCode 拓展程序项目的基本构造

```
.
├── .vscode
│   ├── launch.json     // 用于启动和调试扩展的配置
│   └── tasks.json      // 用于编译 TypeScript 的构建任务的配置
├── .gitignore          // 忽略构建输出和 node_modules
├── README.md           // 扩展功能的描述 markdown
├── src
│   └── extension.ts    // 扩展源代码入口文件
├── package.json        // 扩展清单
├── tsconfig.json       // TypeScript 配置
```

<br>

- Extension Manifest : 每个 VS Code 扩展都必须有一个 package.json 作为其[扩展清单](https://code.visualstudio.com/api/references/extension-manifest)。
- Extension Entry File: 入口文件
```
// The module 'vscode' contains the VS Code extensibility API
// Import the module and reference it with the alias vscode in your code below
import * as vscode from 'vscode';

// this method is called when your extension is activated
// your extension is activated the very first time the command is executed
export function activate(context: vscode.ExtensionContext) {
  // Use the console to output diagnostic information (console.log) and errors (console.error)
  // This line of code will only be executed once when your extension is activated
  console.log('Congratulations, your extension "helloworld-sample" is now active!');

  // The command has been defined in the package.json file
  // Now provide the implementation of the command with registerCommand
  // The commandId parameter must match the command field in package.json
  let disposable = vscode.commands.registerCommand('helloworld.helloWorld', () => {
    // The code you place here will be executed every time your command is executed

    // Display a message box to the user
    vscode.window.showInformationMessage('Hello World!');
  });

  context.subscriptions.push(disposable);
}

// this method is called when your extension is deactivated
export function deactivate() {}
```

## 增强能力

#### Extension Guidelines 编辑器的构造说明

- [Extension Guidelines](https://code.visualstudio.com/api/references/extension-guidelines)

#### Extension Capabilities 扩展能力

- [VS Code API](https://code.visualstudio.com/api/references/vscode-api)
- [Contribution Points](https://code.visualstudio.com/api/references/contribution-points)

#### Guides & Samples 指南和相关项目例子

- [Extension Guide](https://code.visualstudio.com/api/extension-guides/overview)
- [vscode-extension-samples](https://github.com/microsoft/vscode-extension-samples)

#### Testing and Publishing 测试和发布

- 如何为您的扩展添加[集成测试](https://code.visualstudio.com/api/working-with-extensions/testing-extension)
- 如何将你的扩展[发布](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)到 [VS Code Marketplace](https://marketplace.visualstudio.com/)
- 如何为您的扩展设置[持续集成](https://code.visualstudio.com/api/working-with-extensions/continuous-integration)

## 附录

都看到这里了，还不点个赞吗？
<br>
消化官方内容不易，希望对你有所帮助。
<br>
后续会持续更新相关的学习内容，并将最新的文档链接附到此处。

- [VSCode 的构造及部件说明](https://juejin.cn/post/7068193667369926670/)
- [VSCode 拓展清单中的贡献点](https://juejin.cn/post/7069682837955280926/)
- [VSCode 拓展激活事件](https://juejin.cn/post/7069974001547739143/)