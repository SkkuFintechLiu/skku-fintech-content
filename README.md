# SKKU Fintech Content

金融科技研究材料与静态阅读站点的归档仓库。当前根目录以两个压缩包交付，而非可直接运行的研究代码工程。

## 选择下载内容

| 文件 | 内容 | 适合用途 |
| --- | --- | --- |
| [skku_content.tar.gz](skku_content.tar.gz) | Markdown 研究材料，含学术研究与交易策略目录 | 阅读、搜索与编辑原始材料 |
| [skku_site.tar.gz](skku_site.tar.gz) | `skku_site/site/` 静态网页，以及部署脚本和 Nginx 配置 | 本地浏览已生成的阅读站点 |

内容包的 README 描述了更完整的研究工作区结构；压缩包是材料快照，不能据此假定原始数据、研究代码与复现环境均已包含。历史材料与探索性结果应结合对应文档的证据状态阅读。

## 下载与本地阅读

需要 Git、tar；静态站点预览另需 Python 3。在终端执行：

```bash
git clone https://github.com/SkkuFintechLiu/skku-fintech-content.git
cd skku-fintech-content
mkdir -p local-preview/content local-preview/web
tar -xzf skku_content.tar.gz -C local-preview/content
tar -xzf skku_site.tar.gz -C local-preview/web
python3 -m http.server 8000 --bind 127.0.0.1 --directory local-preview/web/skku_site/site
```

打开 [本地站点](http://127.0.0.1:8000/)。使用 Ctrl+C 停止服务。仅阅读 Markdown 时无需启动服务，打开 `local-preview/content/README.md` 即可。

查看清单但不解压：

```bash
tar -tzf skku_content.tar.gz
tar -tzf skku_site.tar.gz
```

## 材料导航

- `academic_research/`：学术研究材料。
- `trading_strategy/`：交易策略研究、方法说明与历史产物。
- 内容包根目录 `README.md` 与治理文件：工作区结构、产物生命周期与研究边界。
- 站点包 `skku_site/site/index.html`：网页阅读入口。

上述路径位于相应压缩包内部。研究结论的有效性应以具体材料的样本、时间范围与验证状态为准。

## 维护说明

当前更新以整体替换归档为主，GitHub 无法直接展示包内 Markdown 的逐行变更。后续可将经整理的公开材料展开为普通目录，并补充从 Markdown 生成站点的构建流程，以便检索、审阅与追踪版本。

部署脚本与 Nginx 配置保留在站点包内；本地预览无需执行它们。正式部署前需按实际服务器环境核对配置。
