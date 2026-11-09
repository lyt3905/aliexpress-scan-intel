# 速卖通选品情报 · 每日扫描简报

AliExpressMonitor 每天扫完速卖通店铺后，把当天新上架的商品整理成一页，发布在这里。

- 入口：<https://lyt3905.github.io/aliexpress-scan-intel/>
- 归档：<https://lyt3905.github.io/aliexpress-scan-intel/archive.html>
- 数据源：本地 AliExpressMonitor 的扫描库（products / scan_discoveries），只读导出
- 图片：直接引用速卖通图床的 350×350 缩略图（`referrerpolicy="no-referrer"`），仓库只放 HTML，不存图

## 页面结构

| 文件 | 说明 |
| --- | --- |
| `index.html` | 固定入口，内容永远等于最新一天的日页 |
| `<YYYY-MM-DD>.html` | 当天新增商品：按店铺归集的卡片（缩略图 / 英文原题 / 店铺 / 入库时间 / 源商品链接） |
| `archive.html` | 历史归档，按日期倒序列出各期件数 |

## 生成方式

由 `build_scan_digest.py` 从扫描库直接渲染（只读打开 sqlite，不改监控库）：

```bash
python build_scan_digest.py --all --out <本仓库目录>
```

日期按 UTC+8 的「入库日」归档；扫描概况按「扫描结果落库时间」归日。
