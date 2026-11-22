# orange-seed

Fieldsbrew 的 **纯源码** 核心 tap（`orangereds` 自建）。

- 定位：所有配方**只有 `[source]`，没有 `[bottle]`**，一律从源码编译。
- 来源：由 `fb convert` 从 Homebrew `homebrew-core` 转换生成。
- 适用：Fieldsbrew（`fb`）——面向 Intel Mac 的包管理器，默认前缀 `/opt/fieldsbrew`。

## 用法

```sh
fb tap orangereds/orange-seed
fb install <name>      # 从源码构建
```

## 与 fields 系 tap 的关系

- `orange-seed`（本仓库）：纯源码，可移植性最好，编译耗时最长。
- `orange-field`：bottle 优先，有可用预编译产物时直接安装。

## 状态

仓库当前为骨架：`Formula/` 目录待生成。
