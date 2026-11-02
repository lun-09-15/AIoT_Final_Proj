> 本檔保留 2026-11-01 初篩時的閱讀與篩選紀錄；後續核對結果及引用版本見 [文獻整理](02_literature_review.md)、references/README.md 及各來源 SOURCE.md。

# 近期文獻與證據初篩

檢索日期：2026-11-01（Asia/Taipei）。
以下明確區分原文發現與本專題適用範圍。未閱讀全文的資料不推定其完整方法或作者自述限制。

## 動機與能源領域

### D1：IEA, Energy Efficiency 2025 — Buildings

- 來源：https://www.iea.org/reports/energy-efficiency-2025/buildings
- 類型：官方產業／政策報告；已讀網頁正文。
- 內容：建築約占全球能源需求 30%；住宅約占建築能源需求 70%。
- 用途：支持家庭能源管理的重要性。
- 適用界線：這是能源需求統計，不能改寫成全球家庭用電占比；也不是 Agent 節能效果的證據。

### D2：The impact of real-time energy consumption feedback on residential gas and electricity usage（2025）

- 來源：https://doi.org/10.1016/j.jeem.2025.103163
- 作者公開稿：https://vringer.nl/docs/Boomsma%20et%20al%202025%20IHD%20JEEEM.pdf
- 類型：Journal of Environmental Economics and Management 原始隨機對照研究；目前核對出版社摘要與作者稿檢索摘錄，全文細節待讀。
- 摘要報告：即時資訊回饋在該研究中對應電力使用減少 2.2%、天然氣減少 6.9%。
- 用途：支持資訊回饋值得研究；提供因果驗證與行為改變的領域研究。
- 適用界線：不是 LLM Agent 實驗；不得把其效果當作本專題預期達成比例。

### D3：A randomized field experiment comparing nudges and boosts for household electricity conservation in student housing（2026）

- 來源：https://www.nature.com/articles/s41598-026-69386-6
- 類型：Scientific Reports 原始實地研究；目前核對出版社索引摘要／討論摘錄，全文受網站存取限制，細節待核對。
- 摘錄報告：以規範回饋與提升能力的提示作比較；兩類介入均相對控制趨勢改善，彼此效果未達統計差異。
- 用途：討論提供資訊與提供可採取建議的差異，以及如何評估使用行為。
- 適用界線：學生住宿族群不代表所有家庭；不能據此斷定兩種策略完全等效。

## AI 技術與 Agent

### A1：Context-aware LLM-based AI Agents for Human-centered Energy Management Systems in Smart Buildings（2025）

- 作者：Tianzhi He、Farrokh Jazizadeh。
- 來源：https://arxiv.org/abs/2512.25055
- 已讀全文 HTML：https://arxiv.org/html/2512.25055v1
- 類型：arXiv 預印本，正式出版狀態另待確認。
- 方法與評估：情境感知能源管理 Agent，120 個查詢、四個住宅資料集、多面向評估。
- 原文報告：能源分析回答正確率 77%；成本管理 49%。原文亦指出程式生成分析的穩定性與重複性問題。
- 本案啟發：分析任務採可核對的工具輸出與標準答案，將數字、工具選擇、證據與限制分開評分。
- 適用界線：原文已涵蓋分析、解釋及評估，不可聲稱既有研究都只有聊天或只做預測。

### A2：LLMs for Agentic Home Energy Management（2026）

- 作者：Sokipriala Jonah。
- 來源：https://arxiv.org/abs/2607.04569
- 已讀全文 HTML：https://arxiv.org/html/2607.04569v1
- 類型：arXiv 預印本，與期刊論文區分標示。
- 方法：工具調用 ReAct Agent，整合價格、氣象、光電與知識庫，對照 MILP 排程。
- 原文重點：原生工具調用與自由文字解析的可靠性不同，需檢查限制條件。作者說明單一家庭配置、單一市場與模擬使用者等限制。
- 本案啟發：分離工具計算與自然語言說明；加入結果及資料條件檢查。
- 適用界線：本案沒有承諾排程最佳化，不直接比較其節省金額或排程最優性。

### A3：Nowcasting the next hour of residential load using boosting ensemble machines（2025）

- 來源：https://www.nature.com/articles/s41598-025-91767-6
- 類型：Scientific Reports 原始研究；目前核對出版社摘要與檢索摘錄，全文受網站存取限制，資料切分與特徵細節待讀。
- 摘要重點：研究下一小時住宅負載，採 boosting 集成，並報告多站點評估。
- 本案啟發：為下一小時預測提供技術參考；模型需與簡單基準比較。
- 適用界線：原文指標不能直接當成本專題目標；先核對預測目標、單位、時間切分與未來資訊是否可用。

## 資料來源

- UCI：https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption
- 法國單一家庭、2006–2010 年分鐘級紀錄；舊資料只用於方法驗證，近期動機另引新來源。
- 三個分表含多種設備，並非所有設備獨立標記；有缺值，沒有真實浪費或故障標籤。

## 研究定位

已有工作整合自然語言、用電分析與設備決策。故本案不以「第一個能源聊天機器人」或「第一個會解釋的能源 Agent」為主張。

本專題定位：設計一個以可追溯證據為核心的家庭用電分析 Agent，結合確定性計算工具、短期預測及能源知識，檢查數字／單位、資料涵蓋與回答依據，並以可重現任務集評估資料不足時的澄清或限制說明。

此定位為範圍明確的專題切入點，不代表已證明全球未解的研究缺口。
