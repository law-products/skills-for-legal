# legal-capabilities

跨领域法律能力，供 13 个业务领域插件共用。

| 技能 | 作用 | 运行时依赖 |
|---|---|---|
| `court-sms` | 识别法院短信，提取案号/当事人/开庭时间，下载文书并归档 | 无 |
| `mineru-ocr` | PDF / 扫描件 / 图片 / 网页转 Markdown，支持表格与公式 | 可选 MinerU Token |
| `wechat-article-fetch` | 抓取微信公众号文章并保存为 Markdown | Playwright |
| `yuandian-law-search` | 元典法条与案例检索，支持语义/关键词/详情 | 元典 API Key |

## 安装

作为 Claude Code 插件安装：

```bash
/plugin marketplace add <path-to-repo>
/plugin install legal-capabilities@claude-for-legal-zh
```

或将 `skills/` 下的目录复制到项目的 `.claude/skills/`：

```bash
cp -R capabilities/skills/* <your-project>/.claude/skills/
```

`mineru-ocr` 的配置路径按 `.claude/skills/mineru-ocr/config/.env` 读取，使用插件方式安装时建议软链到该路径。

## 配置

- `mineru-ocr`：复制 `config/.env.example` 为 `config/.env`，填入 `MINERU_API_TOKEN`（不填则使用免登录轻量接口）
- `yuandian-law-search`：复制 `scripts/.env.example` 为 `scripts/.env`，填入元典 API Key
- `court-sms`：可选复制 `config/user-preferences.example.json` 调整归档目录

## 许可

本目录下的技能为 MIT License，各自保留 `LICENSE.txt`。归属信息见仓库根目录 `NOTICE`。
