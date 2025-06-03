# 🎹 Sample 使用說明（Cubase 範例）

在音樂製作中，使用 Sample（取樣素材）可以有不同的方式，以下是兩種常見的應用模式：

---

## 1️⃣ 模擬樂器演奏的 Sample 使用（Sampler Track）

- 將單一素材（如鋼琴聲、合成器、貝斯等）拉入 **Sampler Track**
- Cubase 會自動讓你透過鍵盤/鋼琴捲軸來改變音高
- 像是將 sample 當成樂器使用一樣來演奏旋律或和弦

### ✅ 功能重點：
- 可以彈奏音階
- 可調 ADSR（Attack, Decay, Sustain, Release）
- 可疊加效果器、濾波器等

### 📍 適合應用：
- 建立旋律型音色（如 vocal chop、synth stab）
- 自製可演奏的特殊樂器音色

---

## 2️⃣ 類似鼓機（Drum Machine）的 Sample 使用

- 將多個不同的 sample（如 Kick、Snare、Hi-Hat）對應到不同的鍵盤音高（如 C1、D1、E1）
- 適合節奏編輯、打擊樂音源

### ✅ 實作方式：
- 可使用 **Groove Agent SE**、**Battery**、或進階版 **Halion**
- 將每個 sample 指定到不同的 MIDI note

### 📍 適合應用：
- 節奏創作
- Lo-Fi/Hip-Hop 鼓組
- Foley / FX Triggering

---

## 🎹 使用 Halion Sonic SE（Cubase 內建）

**Halion Sonic SE** 是 Cubase 內建的多音源播放插件，可用來觸發與分配 sample。  
若你有 Halion 6 或 Halion Sonic Full 版，則功能更完整（如 Sample Mapping、自訂控制器等）。

---

## ⏩ 快速對齊 Sample 節奏：Musical Mode

當 sample 是 loop 或節奏型素材時，可使用 **Musical Mode** 自動對齊 Cubase 專案的節奏。

### ✅ 操作步驟：

1. 在 **MediaBay** 或 Sample Pool 裡找到 sample
2. 確認 audio file 有正確 tempo 設定（如 120 BPM）
3. 勾選 `Musical Mode`
4. 將其拉入 timeline，sample 會自動隨專案節奏調整速度

### 📍 小提醒：
- 適用於 loop、鼓組、吉他段落等
- 不適用於不規則音效或非節奏素材

---

## 📌 小結

| 使用方式 | 說明 | 適合應用 |
|----------|------|-----------|
| Sampler Track | 一個素材彈出不同音高 | Vocal chop、旋律創作 |
| 鼓機式分配 | 不同 Sample 分配在不同 Note | 節奏編輯、打擊樂 |
| Musical Mode | Sample 自動對齊專案節奏 | Loop、節奏型 Sample |

---


## 🎛️ Cubase Sampler Track 製作流程

### ✅ 步驟一：建立 Sampler Track
1. 開啟你的專案。
2. 在左側 **Track List** 空白處右鍵 → 選擇 **Add Sampler Track**。
3. 命名這個 Sampler Track，按下 OK。

---

### ✅ 步驟二：加入音訊樣本（Sample）

- **拖拉方式：**  
  直接將 .wav 或 .aif 音訊檔從 MediaBay 或資料夾拖進 Sampler Track。

- **錄音方式：**  
  錄一段聲音 → 裁剪 → 拖進 Sampler Track 使用。

---

### ✅ 步驟三：用 MIDI 彈奏 Sample

- 在 Sampler Track 上建立 MIDI Part。
- 撰寫 MIDI Note，不同音高會對應不同 Sample 音高。
- 可搭配 MIDI Controller 實時彈奏。

---

### 🎚️ Sampler Track 基本功能

| 功能         | 說明                                     |
|--------------|------------------------------------------|
| **Pitch**    | 設定音高，包含 Root Key（根音）。         |
| **Filter**   | 低通、高通濾波器，含 Resonance。          |
| **Amp Env**  | 音量包絡線（ADSR）：Attack / Decay / Sustain / Release。 |
| **Loop Mode**| 設定 Sample 是否循環播放。                |
| **Glide**    | 滑音功能，連接不同音高會產生 Portamento 效果。 |
| **LFO**      | 加入 Pitch、Filter、Amp 的振盪效果。     |

---

### 🎼 應用範例

- **鼓聲切片：** 將鼓 loop 拖入 Sampler，製作 Drums 重組節奏。
- **Vocal Chop：** 把人聲 sample 拆片，用 MIDI 編排出節奏與旋律。
- **Ambient Pad：** 使用長 sample，拉長 Attack/Release，製作環境音墊。



