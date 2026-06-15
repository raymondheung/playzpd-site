# PlayZPD 官方网站 Codex 受控工作流程

## 仓库职责

- `PlayZPD-Drafts` 用于私人草稿、未批准构想和内容准备。
- `playzpd-site` 是 PlayZPD 官方生产网站的唯一生产仓库。
- 草稿仓库中的内容不得自动发布或自动同步到生产仓库。

## 标准工作流程

1. 在 `PlayZPD-Drafts` 准备和审阅草稿。
2. Ray 明确批准进入生产准备阶段。
3. Codex 从最新 `main` 创建独立分支，不直接编辑 `main`。
4. Codex 只实现已批准的范围，并完成本地检查。
5. Codex 推送分支，等待 Vercel Preview。
6. Ray 检查预览页面、链接、移动端显示、SEO、隐私和业务内容。
7. 只有 Ray 明确批准后，才可通过 PR 合并。
8. 合并、生产发布和回滚均保留人工批准。

## 分支规则

- 每次生产变更必须使用新分支。
- 推荐命名：
  - `draft/growking-group-page`
  - `draft/payment-readiness`
  - `draft/privacy-page`
  - `draft/homepage-refresh`
- 禁止直接推送到 `main`。
- 禁止使用 `git push --force`。
- 禁止绕过 PR、预览或 Ray 审核。

## Codex 可以处理

- 在已批准范围内编辑代码和文档。
- 创建分支、提交变更并准备 PR。
- 执行静态检查、链接检查、秘密扫描和差异检查。
- 整理 Vercel Preview 审核清单。
- 提供可回滚的提交记录和变更摘要。

## 必须由 Ray 明确批准

- 合并到 `main`。
- 生产部署或发布。
- 支付、价格、结账或收款流程。
- 隐私政策、数据收集或未成年人相关内容。
- Analytics、SEO canonical 域名或搜索验证设置。
- Vercel 项目、环境变量、域名或 DNS 设置。

## 停止条件

以下情况必须停止并询问 Ray：

- 范围、目标仓库或生产影响不清楚。
- 发现秘密、个人信息或未成年人资料。
- 变更会影响付款、隐私、Analytics、canonical、Vercel 或 DNS。
- 预览结果与预期不一致。
- 需要修改未获批准的文件或项目。
