# 地球物理學作業 8-2：重力修正與重力異常計算器 (Gravity Corrections & Anomalies)

一個針對地球物理學重力校正（Gravity Corrections）與重力異常（Gravity Anomalies）計算所設計的單頁互動式網頁應用程式。本專案專為部署於 **GitHub Pages** 而設計，包含了完整的理論公式說明、題目詳細解答過程，以及動態重力異常計算工具。

---

## 網頁預覽與功能特色 (Features)

- **題目完整解析**：針對重力測站觀測資料（緯度 $48.1195^\circ\text{ N}$、高程 $487.9\text{ m}$、觀測重力 $980,717.39\text{ mGal}$）提供陸地與海洋兩種情境的完整解答。
- **動態互動計算器**：允許使用者自由輸入緯度、高程/水深、觀測重力值與岩石密度，即時計算重力修正與異常。
- **雙標準公式支援**：支援 **IGF 1967** 與 **WGS-84 (1980)** 兩套國際標準理論重力公式比較。
- **數學公式渲染**：採用 [MathJax](https://www.mathjax.org/) 引擎，完美呈現高解析度的 LaTeX 數學公式。
- **響應式網頁設計 (RWD)**：適應桌機、平板與手機等各種螢幕尺寸。

---

## 理論公式 (Theoretical Background)

### 1. 理論重力 (Theoretical Gravity, $g_{th}$)
- **IGF 1967**:
  $$g_{th}(\phi) = 978031.846 \left(1 + 0.005278895 \sin^2\phi + 0.000023462 \sin^4\phi\right) \text{ mGal}$$
- **WGS-84 (1980)**:
  $$g_{th}(\phi) = 978032.7 \left(1 + 0.0053024 \sin^2\phi - 0.0000058 \sin^2 2\phi\right) \text{ mGal}$$

### 2. 自由空氣修正 (Free-Air Correction, $FAC$)
$$FAC = +0.3086 \times h \text{ (mGal, 其中 } h \text{ 為高程公尺數)}$$

### 3. 布格修正 (Bouguer Correction, $BC$)
- **陸地布格修正**：
  $$BC = 2\pi G \rho h \approx 0.04193 \times \rho \times h \text{ mGal}$$
- **海洋布格修正**（海水密度 $\rho_w = 1.03\text{ g/cm}^3$，地殼密度 $\rho_c = 2.67\text{ g/cm}^3$）：
  $$BC_{ocean} = 2\pi G (\rho_c - \rho_w) d_w \approx 0.04193 \times (\rho_c - \rho_w) \times d_w \text{ mGal}$$

### 4. 重力異常 (Gravity Anomalies)
- **自由空氣異常 ($\Delta g_{FA}$)**：
  $$\Delta g_{FA} = g_{obs} - g_{th} + FAC$$
- **布格重力異常 ($\Delta g_{B}$)**：
  - 陸地：$\Delta g_{B} = \Delta g_{FA} - BC$
  - 海洋：$\Delta g_{B} = \Delta g_{FA} + BC_{ocean}$

---

## 部署至 GitHub Pages 步驟 (Deployment)

1. **建立儲存庫 (Repository)**：
   在 GitHub 上新建一個公開儲存庫，名稱可設為 `gravity-anomaly-calculator`。

2. **上傳檔案**：
   將網頁程式碼儲存為 `index.html`，連同此 `README.md` 一起 Push 至儲存庫的 `main` 分支。

3. **啟用 GitHub Pages**：
   - 前往 GitHub 儲存庫的 **Settings**。
   - 在左側選單點擊 **Pages**。
   - 在 **Build and deployment** > **Source** 選擇 `Deploy from a branch`。
   - 將 **Branch** 設為 `main` 分支，資料夾選擇 `/ (root)`，並點擊 **Save**。

4. **完成**：
   等待約 1-2 分鐘後，即可透過 `https://<YOUR-USERNAME>.github.io/gravity-anomaly-calculator/` 存取網頁。

---

## 技術堆疊 (Tech Stack)

- **前端語言**：HTML5, CSS3, JavaScript (ES6+)
- **公式渲染**：MathJax v3
- **託管平台**：GitHub Pages

---

## 許可證 (License)

本專案僅供教學與學術交流使用 (Educational Purposes Only)。