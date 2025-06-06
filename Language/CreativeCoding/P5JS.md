# P5.js

Property 1: April 11, 2025 10:29 AM

- [x]  第 5 章 - 【創作生成式藝術】條件、迴圈與互動－建構創作規則

花磚 重複的圖形

跟著時間 特定方向 頻率 動作 色彩

- [ ]  第 6 章 - 【創作生成式藝術】增添色彩－玩耍色彩與留下痕跡

- [ ]  第 7 章 - 【創作生成式藝術】進階繪圖 - 畫布操作與編織複雜圖形
- [ ]  第 8 章 - 【互動系統與模擬】函數與物件互動 - 建構無法預測的小世界
- [ ]  第 9 章 - 【互動系統與模擬】韻律、隨機性與噪聲 - 詩意與自然模擬
- [ ]  第 10 章 - 【互動系統與模擬】網頁元素(DOM) - 取得文字、數值和其他輸入
- [ ]  第 11 章 - 【互動系統與模擬】物件導向與向量 - Class 粒子系統
- [ ]  第 12 章 - 【影音互動與即時資料應用】媒體 - 影像、聲音與影片的整合與拆解
- [ ]  第 13 章 - 【影音互動與即時資料應用】使用者影音互動 - 即時串流聲音與影片
- [ ]  第 14 章 - 【影音互動與即時資料應用】資料視覺化與API - 將資料轉化成藝術
- [ ]  第 15 章 - 【程式創作的後續應用】發表作品 - 輸出與使用至不同平台
- [ ]  第 16 章 - 【程式創作的後續應用】後續路線與工具介紹 - OF / Unreal / Unity / TD
- [ ]  第 17 章 - 【加碼單元】文本分析 - 了解文字藝術
- [ ]  第 18 章 - 物理模擬－讓物件自然的落下碰撞
- [ ]  第 19 章 - 3D世界與物件－p5的WebGL應用

[新媒體藝術家](https://www.notion.so/89a7d322920d48069f2451bc1536d993?pvs=21)

### p5.js Cheat Sheet

### 基本設定

```jsx
javascript
複製程式碼
function setup() {
  createCanvas(400, 400); // 設定畫布大小
}

function draw() {
  background(220); // 設定背景顏色
}

```

### 形狀

- **直線**: `line(x1, y1, x2, y2)`
- **矩形**: `rect(x, y, width, height)`
- **圓**: `ellipse(x, y, width, height)`
- **三角形**: `triangle(x1, y1, x2, y2, x3, y3)`

### 顏色

- **設定填色**: `fill(r, g, b)`
- **設定邊框顏色**: `stroke(r, g, b)`
- **設定邊框粗細**: `strokeWeight(weight)`

### 文字

```jsx
javascript
複製程式碼
textSize(32); // 設定文字大小
text('Hello, World!', x, y); // 繪製文字

```

### 互動

- **滑鼠事件**:
    - `mousePressed()`: 滑鼠按下時觸發
    - `mouseReleased()`: 滑鼠放開時觸發
    - `mouseMoved()`: 滑鼠移動時觸發
- **鍵盤事件**:
    - `keyPressed()`: 鍵盤按下時觸發
    - `keyReleased()`: 鍵盤放開時觸發

### 圖片

```jsx
javascript
複製程式碼
let img; // 宣告變數
function preload() {
  img = loadImage('path/to/image.jpg'); // 載入圖片
}
function draw() {
  image(img, x, y); // 繪製圖片
}

```

### 動畫

- 使用 `draw()` 函數持續繪製幀，創造動畫效果。

### 陣列與物件

```jsx
javascript
複製程式碼
let myArray = [1, 2, 3]; // 陣列
let myObject = {key: 'value'}; // 物件

```

### 碰撞檢測

可以使用 `dist(x1, y1, x2, y2)` 來計算兩點間的距離，判斷碰撞。

### 函數定義

```jsx
javascript
複製程式碼
function myFunction(param) {
  // 函數內容
}

```

### 其他常用函數

- **隨機數**: `random(min, max)` // 產生 min 到 max 之間的隨機數
- **重複繪製**: 使用 `for` 迴圈來重複繪製物件

這些是 p5.js 中的一些基本元素，希望對你有幫助！如果你有其他具體問題或需要更詳細的內容，隨時告訴我！

[作業一](https://www.notion.so/13da583732e5807d9a61d3f16474b3dc?pvs=21)

這是一個很有趣的主題！p5.js 非常適合創作互動性高且生動的生物藝術。以下是一些使用 p5.js 繪製生物藝術的主題想法：

### 1. **細胞生態系統**

- 模擬細胞在顯微鏡下的動態，如細胞分裂、合併、移動等行為。
- 可以創建隨機生成的「細胞」或「微生物」，通過程式控制它們在畫布上生長和變化，呈現出有機的生態系統。

### 2. **虛擬珊瑚礁**

- 生成數位珊瑚礁，讓珊瑚隨著「海流」而飄動。
- 使用粒子系統和噪聲函數模擬珊瑚的增長，並添加魚類或其他海洋生物在珊瑚中穿梭，以表現出珊瑚生態的動態平衡。

### 3. **植物生長模擬**

- 創建隨機生成的樹木或植物生長過程，如樹枝分叉、葉片展開等。
- 可以使用 L-system（遞歸結構）來模擬植物的生長規律，使得植物造型更加自然有機。

### 4. **動物行為模擬**

- 通過模擬群體行為（如魚群、鳥群）來展示生物的集體行動。
- 使用簡單的規則，例如「保持距離」「對齊方向」「靠近中心」，來實現魚群或鳥群的互動行為，並讓觀察者感受到群體動態的和諧。

### 5. **生物形態抽象畫**

- 創建抽象的生物形態，如昆蟲的翅膀、葉脈的紋理等。
- 使用噪聲或隨機生成的線條來模擬自然界的有機紋理，讓作品具有自然和不規則的感覺。

### 6. **微生物生態觀察**

- 使用 p5.js 模擬微生物在水滴中的運動。
- 可以設計各種不同形態的微生物，讓它們根據周圍環境隨機運動，互相影響或分裂，模擬出顯微鏡下的觀察體驗。

### 7. **時間推進的生態系統**

- 模擬一片小小的生態系統隨著時間推移的變化，例如植物的生長、枯萎和動物的捕食行為。
- 這可以是一個循環過程，讓使用者看到在不同季節下生態系統的變化，並可通過互動來改變生態平衡。

### 8. **自我繁殖和突變系統**

- 創建自我繁殖的「生物體」，讓它們隨著世代更替而產生小幅突變。
- 可以通過基因算法或隨機生成技術模擬基因的變異，從而展示出自然界中生物遺傳和突變的過程。

### 9. **迷你生物實驗室**

- 用 p5.js 模擬生物實驗，例如不同的化學液體混合後生物細胞的反應。
- 用戶可以像科學家一樣在虛擬實驗室中嘗試調整變數，觀察生物反應的變化。

### 10. **共生或寄生互動**

- 創建虛擬的共生或寄生關係，展示兩種不同生物之間的相互影響。
- 比如模擬樹木與真菌之間的共生，或動物與寄生蟲的關係。

### 1. **細胞生態系統**

- `ellipse()`：用於畫出細胞或微生物的圓形或橢圓形外觀。
- `noise()`：模擬細胞移動的隨機性，讓移動更自然。
- `push()` / `pop()`：控制不同細胞的繪製層次，使細胞之間有獨立的座標和運動。

### 2. **虛擬珊瑚礁**

- `beginShape()` / `endShape()`：創建複雜的多邊形，用於模擬珊瑚的枝葉。
- `vertex()`：與 `beginShape()` 搭配使用，構建珊瑚的分支。
- `noise()`：生成隨機的波動效果，模擬水流中的珊瑚擺動。

### 3. **植物生長模擬**

- `line()`：用於生成樹枝或莖的結構。
- `rotate()`、`translate()`：通過遞迴（例如 L-system）改變樹枝的生長角度，模擬分支的自然形狀。
- `random()`：控制樹枝的分叉方向，使每株植物的結構都略有不同。

### 4. **動物行為模擬**

- `createVector()`：建立位置和速度向量，方便控制每個動物的方向和速度。
- `dist()`：計算動物之間的距離，來調整群體行為（如靠近、遠離）。
- `lerp()`：用於平滑過渡方向，使得群體行為看起來更流暢。

### 5. **生物形態抽象畫**

- `beginShape()` / `vertex()`：創建有機形狀，如昆蟲的翅膀或葉脈。
- `curveVertex()`：可以畫出平滑的有機曲線。
- `noise()`：產生自然紋理，使得抽象畫看起來更接近自然形態。

### 6. **微生物生態觀察**

- `ellipse()`、`arc()`：用於創建不同形狀的微生物。
- `noise()`：生成隨機運動，模擬微生物在水滴中的游動。
- `frameCount`：通過跟踪動畫的幀數來控制不同微生物的動態。

### 7. **時間推進的生態系統**

- `frameCount`：控制季節的推進或時間的流逝。
- `map()`：將時間數值映射到不同的生態狀態，例如隨著季節變化改變植物的顏色。
- `random()`：產生植物隨機生長，使每次觀察的生態系統都稍有不同。

### 8. **自我繁殖和突變系統**

- `random()`：用於引入基因變異，使得後代略有不同。
- `push()` / `pop()`：保存和恢復繪圖設定，以便在每個突變體上應用不同的屬性。
- `for` 迴圈：用於生成後代並進行突變。

### 9. **迷你生物實驗室**

- `mousePressed()` / `mouseDragged()`：設置用戶交互行為，例如點擊或拖拽模擬調整化學液體。
- `map()`：根據用戶輸入將參數映射到不同的生物反應效果。
- `color()`：改變微生物的顏色，以表示不同的實驗反應。

### 10. **共生或寄生互動**

- `dist()`：用於計算不同生物之間的距離，模擬相互作用（例如共生或寄生關係）。
- `lerp()`：讓生物之間的互動顯得更自然，隨著距離減少，互相靠近或影響。
- `push()` / `pop()`：方便管理不同生物的層次，使它們的互動更靈活。