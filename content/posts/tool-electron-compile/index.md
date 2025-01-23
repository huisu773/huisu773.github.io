---
date: '2025-01-23'
draft: false
title: '创建 Electron 应用并使用 Github Action 构建全平台应用'
categories: [Tool]
tags: [Tool,Electron,编程]
---

Electron 本地构建只能构建当前系统的程序，可以使用 Github Action 自动构建全平台的程序。这里记录一下流程。

安装 `create-electron-app`

```bash
npm install -g create-electron-app
```

创建项目

```bash
create-electron-app myproject
cd myproject
```

安装依赖

```bash
npm install --save-dev @electron-forge/publisher-github
```

创建好的项目文件夹内有 `forge.config.js`，在其中添加 publishers 设置：

```json
publishers: [
    {
      name: '@electron-forge/publisher-github',
      config: {
        repository: {
          owner: '<github username>',
          name: '<github repo>',
        },
        draft: true,
      },
    },
  ],

```

添加 Github Action 设置 `.github/workflows/build.yml`

```json
name: Build/release

on:
  push

jobs:
  release:
    runs-on: ${{ matrix.os }}

    strategy:
      matrix:
        os: [macos-latest, ubuntu-latest, windows-latest]

    steps:
      - name: Check out Git repository
        uses: actions/checkout@v1

      - name: Install Node.js, NPM and Yarn
        uses: actions/setup-node@v1
        with:
          node-version: 16

      - name: Build/release Electron app
        uses: wenwuwu/action-electron-forge@v1.4.0
        with:
          package_root: "."
          # GitHub token, automatically provided to the action
          # (No need to define this secret in the repo settings)
          github_token: ${{ secrets.github_token }}

          # If the commit is tagged with a version (e.g. "v1.0.0"),
          # release the app after building
          release: ${{ startsWith(github.ref, 'refs/tags/v') }}
```

如果想要创建新的release，需要在commit中带上tag。

1. 更新 `package.json` 中的版本号，如 `1.0.0`
2. `git commit -am v1.0.0`
3. `git tag v1.0.0`
4. `git push && git push --tags`

这样push后如果build成功会生成一个release的draft，可以选择放出。

