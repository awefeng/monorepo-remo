# 基于pnpm、changesets、truborepo的monorepo

## 初始化
1. `pnpm init`将文件夹初始化为一个工程
2. 手动创建`pnpm-workspace.yaml`，将工程初始化为monorepo
```yaml
packages:
  # all packages in direct subdirs of packages/
  - 'packages/*'
  - 'utils/*'
```

## lint约束
在根目录配置最初的lint，子应用的lint可以覆盖根目录的
子应用创建`.eslintrc.js`，采用`extends`的方式进行覆盖

## 子应用安装其他子应用
`pnpm add mylodash -r --filter demo_a`：在`demo_a`中添加`mylodash`子应用， `-r`表示在根目录运行(不是表示在根目录安装)，`--fliter`表示过滤
