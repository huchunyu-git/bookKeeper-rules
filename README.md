# 自动记账规则库

这个仓库只存放自动记账 App 可公开读取的加密规则库文件，不存放源码、短信原文、通知 dump、银行卡完整信息、明文规则或任何 token。

手机 App 固定读取：

```text
https://raw.githubusercontent.com/huchunyu-git/bookKeeper-rules/main/rules-v1.enc.json
```

更新流程：

1. Codex 修改本地明文规则草稿。
2. Codex 加密生成 `rules-v1.enc.json`。
3. Codex 提交并推送到 GitHub。
4. 手机 App 在“规则库”页面点击“拉取”。
5. App 下载、解密并校验新规则后生效。

规则库应只描述通用解析格式，例如 App 包名、标题关键词、金额正则、商户正则、类别关键词等。不要把个人隐私数据写入规则。

说明：解密密钥随 App 分发，这能防止别人直接复制 GitHub raw 文件使用，但不能抵抗专业反编译。若未来规则包含敏感内容，应改用服务端鉴权。
