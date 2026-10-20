# K 歌混音台

Windows 桌面 K 歌混音工具。將麥克風與 YouTube／瀏覽器伴奏或本機歌曲混合，透過 VB-CABLE 送入 Discord。

此儲存庫只提供編譯後的程式下載與使用說明，原始碼不公開。

## 下載

- [下載 v0.2.0 Windows x64 可攜版](https://github.com/hobby248/karaoke-mixer/releases/download/v0.2.0/KaraokeMixer-Windows-x64-v0.2.0.zip)
- [SHA256 校驗碼](https://github.com/hobby248/karaoke-mixer/releases/download/v0.2.0/KaraokeMixer-Windows-x64-v0.2.0.zip.sha256)
- [版本與下載頁](https://github.com/hobby248/karaoke-mixer/releases/latest)

請完整解壓縮 ZIP，再執行 `KaraokeMixer.App.exe`。保留同資料夾內的 DLL、licenses 與 prerequisites。

## 功能

- 麥克風與伴奏各自調整音量、靜音，提供電平表與人聲回音。
- 內建獨立伴奏視窗：搜尋 YouTube、貼上影片網址、觀看影片本身的歌詞或字幕。
- 伴奏視窗可調整大小、置頂及全螢幕；混音自動擷取該視窗的音訊。
- 可改用指定的外部瀏覽器，或播放本機 MP3／WAV／M4A。
- 支援耳機監聽，並隨附標準版 VB-CABLE 官方原始安裝包與安裝引導。

## 系統需求

建議 Windows 11 x64；指定程序音訊擷取至少需要 Windows build 20348。已包含 .NET 8 與 WPF 執行環境，不需另裝 .NET。

內建伴奏視窗需要網路及 Microsoft WebView2 Runtime。若電腦缺少 Runtime，程式會提供 [Microsoft 官方安裝頁](https://developer.microsoft.com/microsoft-edge/webview2/)。

## 第一次使用

1. 解壓縮並啟動程式。若沒有 VB-CABLE，按「安裝音訊驅動」。
2. 在引導視窗按「啟動 VB-CABLE 官方安裝程式」，同意 Windows 權限提示，再於官方視窗按「Install Driver」。
3. 安裝完成後，儲存其他工作並自行重新啟動電腦。回混音台按「重新偵測」。
4. 「我的麥克風」選實體麥克風；「Discord 混音輸出」選 **CABLE Input**；耳機監聽選你的耳機。
5. Discord 桌面版的輸入裝置選 **CABLE Output**，輸出裝置選耳機。
6. 開啟伴奏視窗，搜尋「歌名 伴奏 歌詞」或貼上 YouTube 網址，選擇帶歌詞的伴奏影片。
7. 回混音台按「開始混音」。本機歌曲則在開始混音後另按「播放」。

請戴耳機。軟體人聲監聽會有延遲；有音效卡直接監聽時，可優先使用音效卡。

## Discord 設定

建議先關閉噪音抑制、回音消除與自動增益，再依試聽結果調整。使用語音活動，適度降低輸入靈敏度門檻，避免伴奏被當成背景音。

直播分享畫面時，避免同時分享同一份伴奏音訊，以免直播音軌與混音麥克風重複播放。

外部瀏覽器模式會擷取所選瀏覽器程序及子程序的聲音，可能包括其他分頁。Discord 請使用桌面版，避免同一瀏覽器內的通話聲音被混回去。

## 目前限制與驗證

已完成 15 項行為測試、9 項主介面檢查，以及內建伴奏視窗的畫面、全螢幕、瀏覽器音訊擷取與 YouTube 搜尋頁載入驗證。

實際麥克風、VB-CABLE 與 Discord 通話的端到端音質、延遲及長時間演唱仍待使用者試唱確認；未宣稱每首 YouTube 影片、字幕或登入流程都已驗證。

目前不提供 AI 去人聲。本程式顯示影片原有歌詞或字幕，不會替純音訊檔自動產生歌詞。

程式不會自動啟動混音、安裝驅動、重新啟動電腦，或修改 Windows／Discord 預設音訊設定。裝置與音量設定儲存在 `%LOCALAPPDATA%\KaraokeMixer`；網站資料儲存在同處的獨立伴奏資料夾。

## 第三方元件

VB-CABLE 由 VB-Audio 提供，是 Donationware，歡迎捐款或購買授權。

- [VB-CABLE 官方來源與捐款](https://vb-audio.com/Cable/)
- [VB-Audio 使用及散布條款](https://vb-audio.com/Services/licensing.htm)

隨附的 `VBCABLE_Driver_Pack45.zip` 為未修改的官方標準版套件，完整使用者條款位於其 `readme.txt`。專業組織部署請依官方條款處理授權。

NAudio、.NET、WPF 與 WebView2 的授權及通知隨下載包附上。第三方元件依各自授權使用與散布。Discord 不包含在下載包內。
