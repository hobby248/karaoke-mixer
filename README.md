# K 歌混音台

Windows 桌面 K 歌工具。把麥克風與 YouTube、瀏覽器或本機伴奏混合，再透過 VB-CABLE 送進 Discord。自己聽到的伴奏和聽眾收到的伴奏可以分開調整。

## 下載

| 頻道 | Windows x64 可攜版 | 校驗碼 | 版本說明 |
| --- | --- | --- | --- |
| 正式版 v1.3.6 | [下載 ZIP](https://github.com/hobby248/karaoke-mixer/releases/download/v1.3.6/KaraokeMixer-Windows-x64-v1.3.6.zip) | [SHA-256](https://github.com/hobby248/karaoke-mixer/releases/download/v1.3.6/KaraokeMixer-Windows-x64-v1.3.6.zip.sha256) | [改版說明](https://github.com/hobby248/karaoke-mixer/releases/tag/v1.3.6) |
| 測試版 v2.1.6 | [下載 ZIP](https://github.com/hobby248/karaoke-mixer/releases/download/v2.1.6/KaraokeMixer-Windows-x64-v2.1.6.zip) | [SHA-256](https://github.com/hobby248/karaoke-mixer/releases/download/v2.1.6/KaraokeMixer-Windows-x64-v2.1.6.zip.sha256) | [改版說明](https://github.com/hobby248/karaoke-mixer/releases/tag/v2.1.6) |

日常使用請選正式版。雙人合唱房目前只在測試版，標示為「**測試中・未驗證**」。歷次更新可查閱 [GitHub Releases](https://github.com/hobby248/karaoke-mixer/releases)。

## 第一次使用

建議使用 Windows 11 x64。Windows 10 會顯示相容性提醒，仍可繼續啟動。內建伴奏瀏覽器需要 WebView2 Runtime，缺少時程式會提供安裝連結。

1. 完整解壓 ZIP，執行 `KaraokeMixer.App.exe`。
2. 若尚未安裝 VB-CABLE，按「安裝音訊驅動」，在官方安裝程式中選 **Install Driver**。重新啟動電腦後，回到混音台按「重新偵測」。
3. 戴上耳機，依下表設定混音台與 Discord 桌面版。

   | 位置 | 項目 | 選擇 |
   | --- | --- | --- |
   | K 歌混音台 | 我的麥克風 | 實體麥克風 |
   | K 歌混音台 | Discord 混音輸出 | **CABLE Input** |
   | K 歌混音台 | 耳機監聽 | 你的耳機 |
   | Discord | 輸入裝置 | **CABLE Output** |
   | Discord | 輸出裝置 | 你的耳機 |

4. 選擇伴奏來源，按「開始混音」。若用本機歌曲，再按「播放」。停止混音時，內建伴奏瀏覽器會一併關閉。

若 Discord 把伴奏壓低或消掉，可依序試關噪音抑制、回音消除和自動增益，每次改一項再試聽。分享畫面時，避免把同一份伴奏再次分享出去。

## 混音與錄音

- **伴奏來源**：內建瀏覽器可開 YouTube 或一般 HTTPS 網頁，也能擷取外部瀏覽器音訊，或播放本機 MP4、MP3、WAV、M4A 等 Windows 可解碼媒體。外部瀏覽器模式可能同時擷取同一瀏覽器其他分頁的聲音。
- **音量**：「伴奏」管聽眾收到的音量，「伴奏監聽音量」管自己的耳機。支援獨立監聽的模式下，兩個欄位都可直接輸入數字，即時生效。100% 為原音量，0% 為靜音。
- **進階調音**：麥克風額外增益、噪音門、回音和殘響。殘響可選 KTV 包廂、小舞台或大廳。本機伴奏可升降 ±12 半音，內建瀏覽器依播放器相容性而定。人聲聽起來跟不上伴奏時，可增加伴奏 OFFSET，延後聽眾輸出與混音錄音中的伴奏。
- **雙軌錄音**：分開儲存混音與乾麥克風 WAV。錄音保存在你選的資料夾。
- **遙控與協助**：同區網可用手機掃 QR Code 並配對。只在可信任的私人網路使用，結束後按「停用」。也可用離線調音碼分享設定，或開啟跨網路協助調音。
- **介面**：支援繁體中文、簡體中文與英文，以及淺色、深色和跟隨 Windows 主題。

## 更新與排查

- **程式更新**：完成錄音並停止混音，再到「遙控與設定」選擇頻道並檢查更新。切換頻道後如需安裝較早的版本，可手動下載對應的 ZIP，完整解壓到新資料夾。
- **更新失敗**：保留 `%LOCALAPPDATA%\KaraokeMixer` 內的設定、草稿與更新備份，改用完整 ZIP 手動更新。
- **Discord 聽眾聽到斷音**：先確認輸入為 **CABLE Output**。可依程式內「使用說明」測試按鍵發話。若 Discord 有「音訊子系統」選項，可切到「傳統」後重新啟動試聽。也可在 VB-CABLE 控制面板查看 Push loss／Pull loss 是否增加。回報時請附版本、伴奏來源及發生時間，也可自行附上雙軌錄音或截圖。[Discord 排查說明](https://support.discord.com/hc/en-us/articles/31623498041623-Discord-Troubleshooting-Guide) · [VB-CABLE 手冊](https://vb-audio.com/Cable/VBCABLE_ReferenceManual.pdf)
- **Windows 啟動提醒**：公開下載包尚未簽章，Windows SmartScreen 可能顯示「無法辨識的應用程式」。請從本頁的 GitHub Releases 下載並核對 SHA-256。

## 回報與授權

使用統計與自動錯誤回報都預設關閉。啟用自動回報後，只會送出版本、日期、錯誤分類與防重複編號。自動回報需要服務端支援。必要服務連線會記錄安裝 UUID、版本、最近連線與來源 IP。可在程式內閱讀完整隱私告知，或使用「問題回報／功能建議」聯絡作者。

作者為 **阿Q x Codex**，Discord ID 為 `quebecliec`。此儲存庫提供編譯後的程式與使用說明，原始碼維持私有。

隨附的 VB-CABLE 是 VB-Audio 提供的 Donationware 官方標準版。其他第三方元件的授權與通知隨下載包附上。[VB-Audio 官方網站](https://vb-audio.com/Cable/) · [VB-Audio 授權條款](https://vb-audio.com/Services/licensing.htm)
