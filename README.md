# 對抗性攻防工作坊
# 🛡️ AI 模型安全評估與自動化加固平台 (AI Model Security & Hardening Platform)

[![Python 3.10+](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/Framework-FastAPI-green.svg)](https://fastapi.tiangolo.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📌 專案緣起與目標
在自駕車、智慧安防、智慧醫療等關鍵 AI 應用場域中，深度學習模型極易受到人眼難以察覺的細微擾動（對抗樣本攻擊）或資料投毒誘發的後門誤判。目前業界缺乏自動化且跨框架的模型安全體檢與加固工具。

本專案旨在打造一個**低門檻、自動化、可量化**的 AI 守護決策平台，協助開發者在模型上線部署前快速診斷資安漏洞，並提供一鍵式防禦加固策略。

---

## ✨ 核心特色與功能

1. **雙模式靈活檢測**
   - **全量評估模式**：同時上傳待測模型與測試資料集，進行全面深度攻防體檢。
   - **僅模型模式**：快速檢測模型架構與基本後門特徵。
   - 支援 PyTorch (`.pt`/`.pth`)、YOLO 等常見深度學習框架。

2. **多維度對抗性攻擊測試**
   - 整合白箱與黑箱演算法：**FGSM**（快速梯度符號法）、**PGD**（投影梯度下降）與 **DPatch**（實體干擾補丁）。
   - 壓力測試模型在極限雜訊與對抗擾動下的良性保留率與抗干擾能力。

3. **神經元後門與異常激活偵測**
   - 採用激活分佈異常分析（Activation Distribution），及早識別模型中潛藏的惡意後門（Trojan / Backdoor）與惡意觸發特徵。

4. **自動化防禦加固引擎**
   - 基於穩健優化（Robust Optimization）與 Min-Max 對抗訓練，尋找最優抗擾權重 $\theta^*$。
   - 提供空間高斯平滑（Randomized Smoothing）等防禦策略，輸出加固前後的 $\Delta\text{AUC}$ 增益與穩健性分數（0~1）。

5. **互動式視覺化診斷報告**
   - 清晰呈現良性準確率 vs. 攻擊準確率 vs. 加固恢復率。
   - 提供安全性曲線圖、敏感度地圖（Sensitivity Heatmap）與雷達分析，讓資安漏洞一目了然。

---

## 🏗️ 系統技術架構

- **前端介面 (Frontend)**：HTML5、CSS3、Vanilla JS、響應式儀表板
- **後端 API 與任務排程 (Backend & Dispatcher)**：FastAPI、Redis 任務快取、Celery 非同步背景排程
- **核心攻防計算引擎 (Core Engine)**：PyTorch、Adversarial Robustness Toolbox (ART)
