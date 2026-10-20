# OceanScope — 海洋智慧監測平台（面試作品）

React + TypeScript + MapLibre GL JS + deck.gl 製作的海洋 WebGIS 展示專案。

## 啟動

請安裝 Node.js 20.19+ 或 22+，接著執行：

```bash
npm install
npm run dev
```

瀏覽器開啟終端機顯示的本機網址（通常為 http://localhost:5173）。

正式打包：`npm run build`。

## 功能
- MapLibre 深色底圖、縮放、拖曳與船舶定位
- deck.gl ScatterplotLayer：模擬海表溫度格點熱力視覺化、船舶點位
- deck.gl PathLayer：模擬洋流向量與船舶航線
- 船舶搜尋、選取、詳情、航線切換
- 時間軸播放，更新模擬海溫與洋流
- RWD 響應式排版

## 資料來源與限制
**全部海洋觀測與船舶數據均為前端模擬資料**，不是即時 AIS、真實海溫或海流，不應用於導航。底圖使用 CARTO 公開底圖服務，運行需要網路。

## 面試展示建議
1. 介紹 React hooks、TypeScript 資料型別與狀態管理。
2. 切換海溫、洋流、船舶三種視覺模式，說明 deck.gl 圖層堆疊。
3. 點選船舶、搜尋船名、飛行定位，展示 WebGIS 互動。
4. 播放時間軸，說明模擬資料如何更新圖層。
5. 說明正式產品如何接 AIS API、海溫格網與洋流資料（例如 NOAA / Copernicus），並加入後端快取、WebSocket、資料驗證、單元測試與 E2E 測試。

## 後續擴充
- 以真實海陸遮罩過濾海溫點，改用網格/紋理渲染提升品質
- 串接合法授權的 AIS 船舶資料與即時推送
- 洋流粒子動畫（GPU/自訂 shader）、等溫線、圖層圖例
- 加入 SQL/PostGIS 空間查詢 API 與資料更新時間標示
