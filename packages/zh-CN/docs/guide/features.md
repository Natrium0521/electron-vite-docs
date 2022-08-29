# 功能

基于 Vite，设计用于 Electron。

## 完全构建

electron-vite 可以智能地为 Electron 的独特环境打包源代码。

- **主进程和预加载脚本：** 无论是在开发还是生产中，这些都会被打包成 CommonJS 模块，并在 Node.js 环境中运行。

- **渲染器：** 在开发过程中，electron-vite 会将 CommonJS / UMD 模块转换为 ES 模块以支持 HMR。在生产过程中，这些将被打包成 IIFE 模块，并在浏览器环境中运行。

## 集中配置和预设配置

当你使用 Vite 来打包你的 Electron 源代码时，项目结构可能是这样的：

```
├──main
│  ├──...
│  └──vite.config.js
├──preload
│  ├──...
│  └──vite.config.js
└──renderer
   ├──...
   └──vite.config.js
```

而在 electron-vite 中，所有的 Vite 配置都合并到一个文件中。项目结构是这样的：

```
├──src/
│  ├──main
│  ├──preload
│  └──renderer
├──electron.vite.config.js
└──package.json
```

此外，electron-vite 内置了很多配置，如`outDir`、`target`、`entry`、`formats`、`external`等，以此进行智能解析和配置检查。

## 渲染进程 HMR

得益于 Vite 极快的 HMR 功能，我们在渲染器开发中使用它。它将极大地提高 Electron 的开发效率。

查阅 [在渲染进程中使用 HMR](/guide/hmr-in-renderer) 部分，了解此功能的更多详细信息。

## Vite 支持

请参阅 [Vite 功能](https://cn.vitejs.dev/guide/features.html) 。