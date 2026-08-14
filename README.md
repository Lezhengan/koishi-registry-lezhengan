# koishi-registry-lezhengan

Koishi 插件市场镜像源，通过 GitHub Actions 定时同步官方 registry 数据到 GitHub Pages。

## 镜像地址

- GitHub Pages: `https://lezhengan.github.io/koishi-registry-lezhengan/index.json`
- jsDelivr CDN: `https://cdn.jsdelivr.net/gh/Lezhengan/koishi-registry-lezhengan@gh-pages/index.json`

## 在 Koishi 中使用

在 koishi.yml 中配置 `market` 插件的 `search.endpoint`（需先安装 `@koishijs/plugin-market`）：

```yaml
market:
  search:
    endpoint: https://lezhengan.github.io/koishi-registry-lezhengan/index.json
```

修改后重启 Koishi 生效。

## 原理

GitHub Actions 每 3 小时从官方源 `https://registry.koishi.chat/index.json` 拉取插件索引，
推送到 `gh-pages` 分支，由 GitHub Pages 提供静态访问。

## 手动触发同步

仓库 Actions 页面 → Sync Registry → Run workflow。
