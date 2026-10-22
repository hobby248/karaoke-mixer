# K 歌混音台

Windows 桌面 K 歌混音工具。將麥克風與 YouTube／瀏覽器伴奏或本機歌曲混合，透過 VB-CABLE 送入 Discord。

作者：阿Q x Codex。聯絡方式：Discord id:quebecliec。

此儲存庫只公開編譯後的程式下載與使用說明，原始碼不公開。

## 下載第一代 v1.0.0

- [Windows x64 可攜版（含青綠麥克風圖示）](https://github.com/hobby248/karaoke-mixer/releases/download/v1.0.0/KaraokeMixer-Windows-x64-v1.0.0.zip)
- [SHA-256 校驗碼](https://github.com/hobby248/karaoke-mixer/releases/download/v1.0.0/KaraokeMixer-Windows-x64-v1.0.0.zip.sha256)
- [版本說明與歷史下載](https://github.com/hobby248/karaoke-mixer/releases)

完整解壓縮 ZIP，再執行 `KaraokeMixer.App.exe`。保留 DLL、licenses 及 prerequisites 資料夾。v0.2.0 使用者請解壓縮到新的資料夾使用；舊版沒有內建更新器，不會自動升級。不要刪除個人設定與錄音。

本版尚未正式簽章，Windows SmartScreen 可能顯示「Windows 已保護您的電腦／無法辨識的應用程式」。程式圖示與混淆不會消除這個警告。

## 功能

- 繁體中文、简体中文、English；淺色、深色、跟隨 Windows 主題。
- 麥克風、伴奏與混音輸出獨立音量、靜音，人聲回音、電平表及耳機監聽。
- 獨立伴奏視窗：YouTube 搜尋、一般 HTTPS 網址、影片原有歌詞或字幕、置頂與全螢幕。網站相容性依各站播放器及限制而定。
- 外部瀏覽器音訊，或本機 MP4、MP3、WAV、M4A 等 Windows 可解碼媒體；本機影片可開啟畫面跟唱。
- 本機伴奏支援 ±12 半音升降 Key；內建瀏覽器提供升降 Key 相容模式，需耳機並依網站實測。外部瀏覽器不支援升降 Key。
- 雙軌 WAV 錄音：混音與乾麥克風分開保存，不自動上傳。
- 同區網手機遙控：QR Code 或網址加八位數配對碼，可調音量、靜音、回音、Key、監聽、語言與主題，以及本機播放與錄音。網站播放器仍在電腦操作。
- 可選擇啟用更新檢查；更新會備份並驗證，不在混音或錄音時安裝。
- 自願使用統計與問題回報各自取得同意；統計預設關閉，個人媒體及音訊不隨回報送出。
- 隨附 VB-CABLE 官方標準版原始安裝包與安裝引導；內含 .NET 8／WPF／ASP.NET Core 執行環境。

## 第一次使用

建議 Windows 11 x64；程序音訊擷取需要 Windows build 20348 以上。內建伴奏視窗需要網路與 Microsoft WebView2 Runtime；缺少 Runtime 時，程式會提供官方安裝連結。

1. 解壓縮並啟動程式，閱讀使用條款。若沒有 VB-CABLE，按「安裝音訊驅動」。
2. 按「啟動 VB-CABLE 官方安裝程式」，同意 Windows 權限提示，在官方視窗按「Install Driver」。完成後儲存工作並自行重新啟動電腦，再回程式「重新偵測」。
3. 「我的麥克風」選實體麥克風；「Discord 混音輸出」選 **CABLE Input**；耳機監聽選耳機。
4. Discord 桌面版輸入選 **CABLE Output**，輸出選耳機。請戴耳機，避免喇叭回授。
5. 選擇伴奏來源並按「開始混音」。本機歌曲另按「播放」。

Discord 可先關閉噪音抑制、回音消除與自動增益，再依試聽結果調整，避免伴奏被消除。分享畫面時避免重複分享同一份伴奏音訊。

外部瀏覽器模式可能擷取同程序其他分頁的音訊，建議使用專門播放伴奏的瀏覽器，Discord 使用桌面版。

## 手機遙控

電腦與手機連到相同區網；電腦可接有線網路。在電腦「手機遙控」選擇私人網路介面並啟用，再用手機掃 QR Code，或輸入畫面網址與配對碼。配對碼有效兩分鐘且限用一次，可重新產生或撤銷授權。音訊需先在電腦啟動。

手機頁面使用未加密 HTTP，只在可信任私人區網使用；不支援跨網路，不需將路由器連接埠公開。Windows 防火牆許可依實際環境僅允許私人網路。遙控預設關閉；關閉遙控視窗不會停止服務，需按停用或關閉程式。手機斷線不停止電腦混音及錄音。

## 資料與限制

設定、備份與伴奏網站資料位於 `%LOCALAPPDATA%\KaraokeMixer`；錄音保存在你選擇的資料夾。更新只替換程式清單內的檔案。使用統計預設關閉，手動回報需另行同意；完整條款與隱私告知可在程式內閱讀。

程式不會自動開啟麥克風、安裝驅動、重新啟動電腦或修改 Windows／Discord 預設音訊設定。不提供 AI 去人聲、YouTube 下載、純音訊自動產生歌詞、歌單或 MP3 錄音匯出。網站廣告、登入、驗證及內容限制由網站處理。

## 驗證範圍

完成 Release 建置、25 項核心測試、15 項實際 HTTP 授權協定測試、16 項 WPF 介面檢查、三語與兩種主題六組視窗檢查，以及 12 項瀏覽器互動檢查。含圖示最終包另驗證 EXE／執行中視窗圖示，並重新完成介面與語言／主題檢查。

實體手機跨裝置連線、防火牆許可、麥克風／VB-CABLE／Discord 實際音質、錄音與長時間影音同步、正式回報送出仍需使用者驗收。不保證所有網站、媒體編碼或電腦都相容。

## 第三方元件

VB-CABLE 為 VB-Audio 提供的 Donationware，歡迎捐款或購買授權：[官方來源](https://vb-audio.com/Cable/)、[使用及散布條款](https://vb-audio.com/Services/licensing.htm)。隨附 `VBCABLE_Driver_Pack45.zip` 是未修改的官方標準版；專業組織部署請依其條款處理授權。

NAudio、.NET、WPF、WebView2、QRCoder、ASP.NET Core 及發行工具的授權／通知隨套件附上。Discord 不包含在下載包內。
