# 本機 Skill 安全安裝與更新防護

這是一個給 Codex / Claude Code / Gemini / OpenCode 等 AI Agent 使用的 Skill，核心目的很簡單：

**安裝任何外部 Skill 或 Agent 指令檔之前，先安全檢查、建立固定本機副本、備份，再安裝。**

它特別防止幾件事：

- 遠端作者日後修改 GitHub / Raw URL 後，自動影響你的本機設定
- Agent 未經同意就執行 `npm`、`npx`、`pip`、`curl`、`git pull` 等外部命令
- Skill 偷讀 Token、API Key、Cookie、`.env`、SSH key 或個人資料
- 自動建立背景程序、排程、Hook 或自動更新
- 用提示詞要求 Agent 隱瞞操作、跳過確認或假裝成功

## 使用方式

把你想安裝的 Skill 檔案，連同這個 Skill 交給 Agent，然後說：

```text
依照《本機安全安裝、來源凍結與更新防護》檢查這份 Skill。
先完成安全掃描並回報，未經我明確同意不得執行外部指令、連線、下載套件或修改全域設定。
通過後再建立固定本機副本、備份並安裝。
```

## 這個 Skill 的原則

1. **只安裝使用者指定的本機檔案**
2. **不自動抓遠端最新版**
3. **先掃描，後安裝**
4. **有外部命令、連線、下載、全域設定修改，都要先問**
5. **更新時必須重新掃描並比對差異**
6. **保留備份與 SHA-256 雜湊紀錄**

## 檔案

- `SKILL.md`：可安裝的 Skill 本體

## 安全提醒

這個 repo 只應保存 Skill 文字，不要放：

- Token / API Key / OAuth 憑證
- `.env`
- SSH key / `.pem` / `.key`
- 本機備份
- 個人工作區路徑或敏感資料

---

# Local Skill Safe Install

A Codex-compatible skill for safely inspecting, freezing, installing, updating, and uninstalling local Skill or Agent instruction files.

## Files

- `SKILL.md` - the installable skill.

## Safety Notes

This repository is intended to keep a fixed local copy of the skill text. Do not add local backups, tokens, API keys, OAuth credentials, or personal workspace paths.

The skill itself emphasizes:

- inspect before installing
- avoid automatic remote updates
- require explicit approval before network, command, or global-setting changes
- keep backups before modifying user-level Agent configuration
- verify installed content with hashes
