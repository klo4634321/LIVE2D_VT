# 自製 VTuber (VT) 指南  

本指南將帶你一步步製作 VTuber（VT），從 AI（stable-diffusion）生成草圖，到 Photoshop 編輯，再到 Live2D 綁定骨架，最終實現 VTuber 的基礎 Live2D 模型。  
<img src="https://img.shields.io/badge/Stable_Diffusion-%23FF6600.svg?logo=stable-diffusion&logoColor=white" alt="Stable Diffusion">
<img src="https://img.shields.io/badge/Photoshop-%2300C8FF.svg?logo=adobe-photoshop&logoColor=white" alt="Photoshop">
<img src="https://img.shields.io/badge/Live2D_Cubism-%2300C300.svg?logo=live2d&logoColor=white" alt="Live2D Cubism">
<img src="https://img.shields.io/badge/VTube_Studio-%230080C0.svg?logo=vtube-studio&logoColor=white" alt="VTube Studio">

---

## 🔧 需要的工具  
1. **Stable Diffusion**（或其他 AI 生成工具） – 生成初步角色草圖  
2. **Photoshop（或其他繪圖軟體）** – 處理角色圖層與切割關節  
3. **Live2D Cubism Editor** – 製作 Live2D 模型  
4. **VTube Studio** - 完成人臉到 Live2D 的映射
---

## 🚀 製作步驟  

### 1️⃣ Stable Diffusion 生成草圖（`sketch.png`）  
首先，我們使用 **Stable Diffusion** 來生成角色的草圖，作為 VTuber 的基礎設計。  
[Notion筆記](https://www.notion.so/Stable-Diffusion-a190f738f4e14d838700ec5a85351084#1b34a9fbc49680c7a610e8e3506f6b1e)

**✅ 步驟**：  
- 準備草圖<img src="https://github.com/user-attachments/assets/19b80ea4-7883-43cd-836e-94425af078b2" width="100">
- 設定適當的 `prompt`（提示詞）來描述角色外觀，例如：  anime girl, silver hair, blue eyes, wearing kimono
- 選擇合適的模型（例如 `AnythingV5`、`Counterfeit` 等）  
- 生成草圖，並手動挑選最符合需求的版本  
- 另存為 `sketch.png`，準備進行後續處理  
<img src="https://github.com/user-attachments/assets/35033cc8-1c57-45ef-84db-f5ffbd3ab434" width="100">

- 利用ChatGPT將草圖重新繪製成適合Live2D圖並重命名為"Character.png"
<img src="https://github.com/user-attachments/assets/1b2a0d1b-8dde-4e7c-b62d-111b09da2673" width="100">



**✅ 補充建議**：  
- 可透過 **ControlNet** 或 **Inpaint** 來調整細節，例如更改表情或修正手部  
- 若需要更清晰的線稿，可使用 **AI Upscaler** 來提高解析度  

---

### 2️⃣ 使用 Photoshop 切割角色部件  
Stable Diffusion 生成的圖像是一體成型的，我們需要手動拆分成不同的圖層，讓 Live2D 可以獨立控制各個部件。  
[Notion筆記](https://dark-starfish-f58.notion.site/Photoshop-1c54a9fbc49680d18ec8f66a4882d10e?pvs=4)
**✅ 步驟**：  
1. **導入 `Character.png` 到 Photoshop**  
2. 使用 **選取工具（Pen Tool / Lasso Tool）** 切割角色的關鍵部位，包括：  
 - **臉部**（眉毛、眼睛、瞳孔、嘴巴）  
 - **頭髮**（前髮、側髮、後髮）  
 - **身體**（衣服、手臂、腳）  
3. 每個部件分開放道不同圖層。
4. 儲存為 **PSD 檔案**，確保所有部件都在不同圖層  

**✅ 補充建議**：  
- 盡量保持角色的 **對稱性**，這樣在 Live2D 綁定時比較容易  
- 眉毛、眼睛、嘴巴的表情可以 **額外繪製不同狀態**（如閉眼、張嘴）  

---

### 3️⃣ Live2D Cubism 綁定骨架  
在 **Live2D Cubism Editor** 中，我們將角色的各個部件綁定骨架，使其能夠動態變化。  

**✅ 步驟**：  
1. **導入 Photoshop 匯出的 PSD 檔案**  
2. **建立模型**（Model Workspace）並調整圖層位置  
3. 使用 **Deformer（變形工具）** 為角色部件添加控制點  
4. **綁定骨架（Rigging）**：  
 - 綁定 **眼睛、嘴巴** 的變形  
 - 綁定 **頭部旋轉（X/Y/Z）**  
 - 綁定 **身體擺動、頭髮物理效果**  
5. 測試 **動態效果**，調整表情與動作範圍  
6. 匯出為 **`.moc3`** 檔案，準備在 VTuber 軟體中使用  

**✅ 補充建議**：  
- **參考官方範例**（Live2D 官網有提供免費模型）來學習綁定技巧  
- **增加物理效果**，讓角色的髮絲與衣服有更自然的動態  

---

## 🎥 進一步應用  
- 可以將 **`.moc3`** 檔案導入 **VTube Studio** 或 **PRPRLive** 來進行即時面部捕捉  
- 若想進一步增加 **手勢控制、全身動作**，可以搭配 **Leap Motion / VR Tracking**  

這樣，你的 VTuber 角色就誕生了 🎉！  
![demonstrate](https://github.com/user-attachments/assets/c34bc729-9644-462d-af6d-8d29c007e775)

---

## 📌 結語  
本指南提供了從 AI 生成角色，到 Live2D 綁定的完整流程。如果想要更精細的表現，可以手繪細節，並深入學習 Live2D 的高級功能（如物理演算、表情變換）。  

希望這份 README 幫助你順利製作屬於自己的 VTuber！🚀
