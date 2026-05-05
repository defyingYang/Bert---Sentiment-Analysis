# Movie Review Sentiment Analysis with BERT - 電影評論情緒分析

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-ee4c2c.svg)
![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-Transformers-yellow.svg)

## 📌 專案簡介
本專案為 **國立中央大學（National Central University）資訊管理系** 課程作業。利用 Google 開源的預訓練模型 **BERT (Bidirectional Encoder Representations from Transformers)**，針對 IMDB 電影評論資料集進行二元情緒分類（正面/負面）。

這項實驗展示了如何利用遷移學習（Transfer Learning）技術，在有限的運算資源下，透過微調（Fine-tuning）頂尖的 NLP 模型來達成極高的文本分類準確度。

## 📊 資料集說明
- **名稱**: [Large Movie Review Dataset (IMDB)](https://aclanthology.org/P11-1015.pdf)
- **內容**: 包含 50,000 則極具極性的電影評論（25,000 訓練集，25,000 測試集）。
- **特點**: 評論文本長度不一，包含豐富的語言特徵與強烈的情感表達，是衡量 NLP 模型效能的經典基準測試。

## 🛠 我完成的核心任務 (TODO 1-7)

在本專案中，我獨立完成了從文本標記化到模型效能評鑑的完整流程：

1.  **TODO 1: 環境建置與封包導入 (Dependencies)**
    - 安裝並導入 `transformers`, `torch`, `scikit-learn` 等深度學習與 NLP 相關套件。
2.  **TODO 2: BERT Tokenizer 配置 (Text Tokenization)**
    - 使用 `BertTokenizer` 將原始評論文本轉換為 BERT 專用的 Token IDs。
    - 設定 `max_length` 並進行 Padding 與 Truncation 處理，確保模型輸入維度一致。
3.  **TODO 3: Attention Masks 處理 (Masking)**
    - 建立 Attention Masks，引導模型區分真實的語意資訊與填充用的 Padding Token。
4.  **TODO 4: 資料加載器建置 (DataLoaders)**
    - 將處理後的 Tensor 包裝進 `DataLoader` 中，實現 Batch 訓練以提升運算效率並控制顯存佔用。
5.  **TODO 5: BERT 模型微調架構 (Model Fine-tuning)**
    - 載入預訓練的 `bert-base-uncased` 模型。
    - 凍結/微調權重，並在頂層添加線性層以進行特定任務（二元分類）的預測。
6.  **TODO 6: 優化器與調度器設定 (Optimization)**
    - 配置 `AdamW` 優化器與學習率調度器（Learning Rate Scheduler），實現訓練過程中的動態學習率調整。
7.  **TODO 7: 訓練循環與準確度評估 (Loop & Evaluation)**
    - 實作完整訓練循環，包括前向傳播、損耗計算、反向傳播與參數更新。
    - 在測試集上計算 **Accuracy** 與 **F1-score**，量化模型對複雜文本情緒的判斷能力。

## 🚀 學習成果
- 深入理解 Transformer 架構中的 Self-attention 機制。
- 實踐了 HuggingFace 生態系中的模型微調工作流。
- 學會處理自然語言處理中的文本截斷與長度對齊問題。

---
*註：本專案程式碼參考自 [Hugging Face 官方文檔](https://huggingface.co/) 並根據作業需求進行大量客製化實作。*