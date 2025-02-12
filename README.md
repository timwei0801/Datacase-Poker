# 德州撲克 AI 決策輔助系統：牌桌識別 AI 決策輔助系統
# Texas Hold'em Poker Robot: Table Recognition AI Decision-Making Assistance System

## 專案概述

本系統代表了德州撲克遊戲輔助技術的突破，通過整合最新的人工智慧技術，為線上撲克玩家提供前所未有的決策支援。系統的核心優勢在於結合了先進的影像辨識技術、深度學習模型以及 Game Theory Optimal (GTO) 策略分析，創造出一個完整的智能決策生態系統。

在技術層面，本系統採用了深度學習框架進行影像識別，運用卷積神經網路（CNN）準確識別牌面信息，同時通過強化學習算法不斷優化決策模型。系統的 GTO 策略分析基於納什均衡理論，能夠在複雜的遊戲環境中計算出理論最優解，為玩家提供最具數學支撐的策略建議。

![影像識別示例圖](./images/影像識別示例圖.png)

上圖展示了系統的影像識別功能，通過精確的圖像分割和特徵提取，實現了超過 95% 的識別準確率。系統能夠即時捕捉並分析包括牌面、籌碼量、玩家位置等關鍵信息，為後續的策略分析提供精確的數據基礎。

## 系統架構

### 整體架構設計

本系統採用現代化的三層式架構，這種架構設計不僅確保了系統的高度模組化，同時也為未來的功能擴展提供了極大的靈活性。系統的每一層都經過精心設計，以實現最優的性能和可維護性：

![系統流程架構圖](./images/系統流程架構圖.png)

展示層（Presentation Layer）採用了響應式設計，確保系統在不同設備上都能提供最佳的使用體驗。我們使用 WebSocket 技術實現即時通訊，保證了策略建議的及時傳遞，延遲控制在 500 毫秒以內。

業務邏輯層（Business Logic Layer）整合了多個關鍵組件：
- 影像處理模組：基於 OpenCV 和深度學習模型
- 策略分析引擎：結合 GTO 理論和強化學習算法
- 數據處理中心：處理即時數據流和歷史數據分析

資料持久層（Data Persistence Layer）使用 MySQL 叢集確保數據的可靠性和可擴展性，實現了高可用性的數據存儲方案。

### 資料庫設計

系統的資料庫設計採用了完整的實體關聯模型（E-R Model），通過精心的數據結構設計確保了數據的完整性和查詢效率：

![E-R Model](./images/E-R%20Model.png)

數據庫設計的核心特點包括：

1. 用戶管理系統
   - 採用 bcrypt 加密算法保護用戶密碼
   - 實現了完整的權限管理機制
   - 支持多級用戶角色設計

2. 遊戲記錄管理
   - 詳細記錄每局遊戲的完整信息
   - 支持複雜的多維度數據分析
   - 實現了高效的查詢優化機制

3. 策略分析存儲
   - 保存 AI 決策過程的關鍵數據
   - 支持策略效果的追蹤和分析
   - 實現了完整的數據回溯機制

### 理論基礎

#### GTO 策略分析

![GTO理論圖](./images/GTO理論圖.png)

Game Theory Optimal (GTO) 策略是現代德州撲克理論的核心，代表了一種無法被對手利用的均衡策略。我們的系統在 GTO 理論的基礎上，實現了以下關鍵特性：

1. 頻率平衡
   - 在不同街數維持最優的行動比例
   - 動態調整詐唬和價值下注的頻率
   - 確保策略的不可被利用性

2. 範圍優化
   - 科學分配強牌和弱牌的使用比例
   - 維持合理的詐唬與價值下注平衡
   - 實現最優的期望值最大化

3. 動態調整
   - 根據對手策略即時調整行動方案
   - 通過機器學習不斷優化決策模型
   - 實現策略的自適應優化

#### Nash 均衡策略

![Nash均衡圖](./images/Nash均衡圖.png)

納什均衡策略在我們的系統中扮演著關鍵角色，通過複雜的博弈論計算，系統能夠：

1. 計算最優反應
   - 分析對手策略範圍
   - 計算理論最優對策
   - 優化期望收益

2. 策略平衡
   - 維持混合策略的均衡
   - 避免被對手利用
   - 最大化長期收益

## 系統功能

### 主要界面

系統的主界面經過精心設計，整合了多項先進功能：

![系統主畫面](./images/系統主畫面.png)

主界面的核心功能包括：

1. 即時影像分析
   - 高精度牌面識別
   - 實時籌碼計算
   - 位置優勢分析

2. 策略建議生成
   - GTO 策略計算
   - 期望值分析
   - 風險評估報告

3. 數據可視化
   - 實時獲勝機率展示
   - 策略效果追蹤
   - 歷史數據分析

### 用戶驗證系統

系統採用多層次的安全驗證機制：

![登入頁面](./images/登入頁面.png)
![註冊頁面](./images/註冊頁面.png)

用戶驗證系統的特點：

1. 安全性設計
   - 採用 JWT token 認證
   - 實現 OAuth 2.0 協議
   - 支持二步驗證機制

2. 用戶管理
   - 完整的用戶資料管理
   - 權限級別控制
   - 操作日誌記錄

### 核心功能架構

系統的核心功能架構展現了其強大的分析能力：

![主要架構](./images/主要架構.png)

核心功能包括：

1. 影像識別系統
   - 採用深度學習模型
   - 實現實時圖像處理
   - 支持多種遊戲界面

2. 決策分析引擎
   - 整合 GTO 策略
   - 實現動態策略調整
   - 提供即時決策建議

### 歷史記錄分析

系統提供完整的歷史數據分析功能：

![歷史紀錄查詢頁面](./images/歷史紀錄查詢頁面.png)

歷史記錄分析系統具備：

1. 數據追蹤
   - 完整的遊戲記錄保存
   - 詳細的決策過程記錄
   - 策略效果評估報告

2. 分析工具
   - 高級統計分析功能
   - 趨勢圖表生成
   - 自定義報告導出

## 系統需求

### 硬體配置要求

為確保系統的最佳性能，建議使用以下配置：

1. 處理器
   - Apple M 系列晶片（M1 或更新版本）
   - 支持神經網路引擎
   - 具備高效能運算能力

2. 記憶體
   - 16GB RAM 以上
   - 建議使用高速記憶體
   - 支持大型數據處理

3. 存儲設備
   - 256GB 以上固態硬碟
   - 高速讀寫能力
   - 足夠的數據存儲空間

4. 顯示系統
   - 支援 1920x1080 解析度以上
   - 色彩精確度高
   - 反應速度快

### 軟體環境需求

系統運行需要以下軟體環境：

1. 作業系統
   - macOS 最新版本
   - 系統更新至最新狀態
   - 安裝所需的系統組件

2. 開發環境
   - Python 3.8+
   - 相關函式庫最新版本
   - 完整的開發工具鏈

3. 資料庫系統
   - MySQL 8.0+
   - 優化的數據庫配置
   - 完整的備份機制

4. 瀏覽器要求
   - Chrome 或 Safari 最新版本
   - 支持 WebSocket 協議
   - 啟用必要的瀏覽器功能

## 操作流程

### 基本操作指南

系統操作流程經過精心設計，確保用戶能夠輕鬆上手：

1. 系統啟動階段
   - 完成系統登入驗證
   - 檢查系統組件狀態
   - 初始化必要服務

2. 即時操作階段
   - 通過快捷鍵觸發功能
   - 即時接收分析結果
   - 執行策略建議

3. 系統結束階段
   - 保存重要數據
   - 生成分析報告
   - 完成安全登出

## 研究成果

### 系統效能評估

通過大量測試和實際應用，系統展現出優異的性能：

1. 影像識別能力
   - 準確率達到 95% 以上
   - 穩定的識別表現
   - 適應各種遊戲環境

2. 系統反應速度
   - 平均延遲低於 500 毫秒
   - 穩定的性能表現
   - 高效的資源利用

3. 策略優化效果
   - 提升玩家勝率約 25%
   - 顯著降低決策失誤
   - 持續的學習改進

### 創新特點

系統在多個方面實現了技術創新：

1. 技術整合
   - 深度學習技術應用
   - GTO 理論實踐
   - 即時分析能力

2. 實用價值
   - 提升遊戲體驗
   - 優化決策品質
   - 強化學習效果

## 開發團隊

本系統由淡江大學統計學系數據科學碩士班開發：

開發成員：
- 魏祺紘：負責資料庫設計和使用者介面開發
- 李昇峰：負責系統架構設計和 AI 模型開發

指導教授：
- 高君豪 博士：提供理論指導和技術支持

## 技術支援

我們提供完整的技術支援服務：

1. 問題解決
   - 專業技術團隊支援
   - 快速響應機制
   - 定期系統維護

2. 培訓服務
   - 完整的使用指南
   - 定期的培訓課程
   - 技術文檔更新

## 授權聲明

本系統為學術研究成果，著作權歸屬淡江大學統計學系數據科學碩士班。系統使用需遵守以下規範：

1. 使用限制
   - 僅供學術研究使用
   - 禁止商業用途
   - 需註明出處

2. 權限說明
   - 保留所有權利
   - 需經授權方可使用
   - 遵守相關法規

---
*註：本系統開發目的在於學術研究，使用時請務必遵守各線上撲克平台的使用規範。*
