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

仓库已收录 **8736 个配方**（`Formula/` 扁平存放，每个包一个 `.toml`）。

清洗情况（相对 Homebrew 自动转换的原始产物）：

- 删除全部 `[bottle]` / `[bottle.tags.*]` 段 —— 手上没有可用的 macOS 产物，而原数据里唯一的 bottle 是 Linux x86_64 构建，在 Intel Mac 上装不了，留着反而会被误选。
- 删除被误当成包名的版本号依赖（`fb convert` 解析 `depends_on :xcode => ["16.0", :build]` 时的残留），全库共 79 处。
- 修正 `bzip2`、`pkgconf` 的 `sha256`。
- 8736 个配方全部通过 TOML 解析校验，无非法依赖、无指向缺失配方的悬挂依赖。
