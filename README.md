# obsidian-cli
Obsidian CLI 介紹

## 介紹
Obsidian 1.12.4 在 2026 年 2 月 27 日 推出時附帶官方 Command Line Interface，這讓 Vault 的任何操作（建立記事、套用範本、搜尋、批次更名等）都可以透過終端機執行，進而與排程、自動化腳本與像 Claude Code 這類的 AI 工具無縫整合。這個 CLI 不需要額外付費；只要更新至 1.12.4（或以後的版本）並在設定裡啟用，就能直接進入 Obsidian 的新「指令模式」。

## 安裝 Obsidian CLI

Obsidian CLI 會隨著官方桌面應用一起安裝；只要安裝桌面版並在「設定 → 一般」勾選「Command line interface」，terminal 就能直接呼叫 `obsidian` 系列指令。下列步驟會協助你先裝好 Obsidian，然後啟用並驗證 CLI 是否可用。

### macOS

1. 使用 Safari 或其他瀏覽器前往 Obsidian 官方下載頁面（例如 https://obsidian.md/download），點選 macOS（DMG）版本取得最新版安裝包。
2. 打開下載完成的 DMG，將 Obsidian 拖放到 `Applications` 資料夾並執行。
3. 在 App 中確認版本為 1.12.4 或更新，開啟「設定」→「一般」並啟用「Command line interface」開關。
4. 開啟終端機（Terminal），輸入 `obsidian help` 檢查 CLI 是否已準備好，之後就可以直接使用 `obsidian ...` 系列指令。
5. 若偏好在終端機安裝，可使用 Homebrew 安裝最新的 Obsidian：`brew install --cask obsidian`，完成後同樣到 App 中啟用 CLI。

### Windows

1. 透過 Obsidian 官網下載 Windows 64-bit Installer（`.exe`）或選用 Chocolatey、Winget 等套件管理器的官方套件。
2. 以系統管理員權限執行安裝程式並依序完成安裝，建議安裝至預設的 `Program Files` 路徑以便系統變數自動設定。
3. 開啟 Obsidian，確認版本為 1.12.4 或更新，同樣在「設定」→「一般」打開「Command line interface」開關。
4. 開啟 PowerShell 或命令提示字元，執行 `obsidian help`，若看到指令清單代表 CLI 已就緒。
5. 想用終端機安裝可以用 `winget install --id=Obsidian.Obsidian -e` 或 `choco install obsidian`，完成後再在 App 裡啟用 CLI 開關。

## 核心能力
- **建立/讀取日誌與 Daily Note**：透過 `obsidian daily` 和 `obsidian daily:append` 經常性捕捉想法，將 Obsidian 變成每日工作流程的入口。
- **全 Vault 搜詢與內容操作**：`obsidian search query="..."` 或 `obsidian search:context` 可以找出任意片段，`obsidian files` 統計檔案狀態。
- **檔案與標籤維護**：`obsidian rename` / `move` 命令會自動維持內部連結，避免因重整檔名而破壞網絡結構。
- **開放 API 與 TUI 支援**：CLI 同時提供即時 TUI 檢視與開發者命令，方便串接腳本、Cron 任務或以 shell 監控 Vault。

## 啟用方式
1. 確保 Obsidian 版本為 1.12.4 或更新版本。
2. 開啟「設定」→「一般」並啟用「Command line interface」開關。
3. 完成註冊後，在終端機執行 `obsidian help` 會呈現完整指令集，即可開始使用。

## Quick Start（測試 CLI）

1. 在終端機先執行 `obsidian --version`，確認 Obsidian 桌面版已安裝並可回應版本號。
2. 再執行 `obsidian help`，理想情況會列出所有 CLI 命令，表示 CLI 已啟用且可用。
3. 嘗試用 `obsidian search query="test"` 或 `obsidian files` 類似指令操作一個已開啟的 Vault，確保 CLI 不會回報錯誤。
4. 若遇到錯誤，確認 Obsidian App 已打開且 CLI 開關開啟，必要時重新啟動 App 或終端機再試。
5. **命令必須在 Vault 目錄或使用 `--vault` 指定路徑執行；否則 CLI 會啟動 Obsidian 卻不會處理任何檔案**。
