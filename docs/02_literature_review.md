# Energy Detective：Related Work 與文獻整理表

第 1–7 節整理六筆核心來源與資料集說明；第 8 節補充兩筆 Deep Research 來源。

以六筆核心來源建立研究脈絡：三筆能源領域來源（含一份官方報告）、三篇 AI 技術研究。UCI 資料集說明另列為資料來源。這是目前的範圍化比較，不是系統性文獻回顧，也不代表已證明全球首次創新。

## 1. 能源領域與資訊回饋

IEA 的 2025 年報告將住宅能源效率列為重要課題；其中住宅約占建築能源需求的 70% [1]。這項統計描述所有能源，不是家庭電力占比。對本專題而言，能源背景用來說明研究重要性，不能據此推導 Agent 能達成的節電幅度。

Boomsma 等人的隨機對照研究追蹤荷蘭家庭，以即時能源顯示器提供資訊回饋，報告電力使用減少 2.2%、天然氣使用減少 6.9% [2]。Paunov 等人則比較社會規範回饋與能力提升提示，在學生住宅情境中發現兩種策略相對控制趨勢均有改善，但彼此差異未達統計顯著 [3]。這些研究說明資訊及建議值得研究，也提醒我們：提供回答、使用者採取行動、最後節電，是不同的驗證層次。

## 2. AI 預測與能源管理 Agent

He 與 Jazizadeh 已提出具情境感知能力的能源管理 Agent，整合資料分析、設備互動與多面向評估 [4]。Jonah 等人的新版研究則以工具調用 Agent 執行多設備排程，指出自然語言解釋與實際動作必須分別檢查 [5]。因此，本專題的定位不能只是將 LLM 接上能源資料，也不能聲稱既有能源 Agent 完全沒有可靠性評估。

在預測方法上，Muqtadir 等人以 boosting 集成分析下一小時住宅負載，顯示方法表現會隨站點而變 [6]。本專題採不同的單一家庭資料，須重新建立基準與時間序列測試，不能沿用其數值作為本系統成效。

## 3. Article Summary Table

下表包含八個欄位。Limitation 內明確區分「作者指出的限制」與「本專題比較後的適用範圍判斷」。非 AI 領域研究如實填寫不適用，不為符合欄位而虛構 AI 方法。

| Ref. | Year | Problem | AI Method | Domain Knowledge | Dataset | Findings | Limitation |
|---|---|---|---|---|---|---|---|
| [1] IEA | 2025 | 住宅能源效率的需求與改善方向 | 不適用；官方能源統計與政策分析 | 住宅能源用途、設備效率、氣候與地區差異 | IEA 能源統計與跨國部門分析 | 住宅約占建築能源需求 70%；家庭能源結構因地區而異 | 本專題適用範圍：宏觀能源背景，不能證明家庭 Agent 效果，不能當作家庭用電占比 |
| [2] Boomsma et al. | 2025 | 即時能源資訊是否改變住宅能源使用？ | 不適用；RCT 與統計分析 | 智慧電表、回饋、成本顯著性與行為改變 | 荷蘭七地區 802 戶分析樣本，電力／天然氣紀錄與問卷 | 研究報告電力減少 2.2%、天然氣減少 6.9% | 作者提及問卷自我選擇；本案判斷：自願申請、使用顯示器的研究情境，不等同對話 Agent |
| [3] Paunov et al. | 2026 | 社會比較回饋與能力提升提示的成效是否不同？ | 不適用；24 週隨機實地實驗 | 社會規範、節能能力、動機與參與程度 | 瑞典學生住宅，140 戶納入分析；電表與問卷；OSF 提供資料 | 兩種介入均改善相對控制趨勢；彼此差異未達顯著 | 作者指出學生樣本與自願參與、可能資訊分享、參與度衰退；不能推論兩策略完全等效 |
| [4] He & Jazizadeh | 2025 | 如何以自然語言支援具情境感知能力的能源管理？ | LLM Agent、工具調用、程式分析與知識檢索 | 建築設定、用電、費率、設備狀態與使用偏好 | Pecan Street 四戶案例，15 分鐘資料；120 個查詢 | 作者報告能源分析回答正確率 77%、成本管理 49% | 作者指出生成程式分析的穩定性／重複性問題；設備控制使用模擬 API。本案不以此百分比直接評分自有系統 |
| [5] Jonah et al., v2 | 2026 | 如何把自然語言需求轉為符合限制的家庭設備時程？ | ReAct、原生工具調用、知識庫；與 MILP 比較 | 動態電價、光電、設備時限、功率上限與可行性 | 英國 Octopus Agile、氣象／光電估計、家庭需求；歷史資料與模擬請求 | 原生工具介面較自由文字解析可靠；一般低成本表現不能保證衝突情境下遵守限制 | 作者指出單一家庭配置與市場、有限設備類型、歷史週期及模擬請求；未驗證長期真實家庭節省 |
| [6] Muqtadir et al. | 2025 | 如何改善下一小時住宅負載預測？ | LightGBM、XGBoost、CatBoost 集成 | 負載時間變化、氣象、站點差異、缺值與異常處理 | Building Data Genome Project 2 的住宅用途資料與氣象／metadata；13 站點評估 | 在原文比較中呈現集成預測效果，且站點表現有差異 | 本案比較判斷：資料不是 UCI 單戶；工作重點為負載預測，不是自然語言回答與證據鏈評估 |

## 4. Existing Research → Limitations → Research Gap → Our Project

| 階段 | 本專題的歸納 |
|---|---|
| Existing Research | 已有家庭能源回饋實驗、短期負載預測，以及結合工具的能源 Agent。 |
| Limitations | 行為研究不直接驗證 Agent 分析；預測誤差不等於回答正確性；Agent 研究亦顯示計算、工具執行及限制遵守可能出錯。 |
| 本專題聚焦的問題 | 在單戶歷史資料回放的五類任務中，如何讓回答的數字、時間、單位與建議能追溯到工具輸出，並在資訊不足時適當追問或縮限結論？ |
| Our Project | 規劃 Energy Detective：由 Agent 選擇分析工具，結合能源知識，記錄分析依據並檢查回答；分別評估預測、分析任務與證據一致性。 |

以上是本組選擇的可驗證研究切入點，不宣稱「沒有任何既有系統檢查可靠性」或「本專題首次提出證據鏈」。固定計算工具及結果檢查是待驗證的設計選擇，不是已證明能消除錯誤的技術。

## 5. 對方法與評估的設計啟發

1. 電量、差值、比例由分析工具計算；LLM 負責協調與解釋，不把自由文字計算當成唯一依據。
2. 回答能對應資料版本、時間區間、有效資料狀態、分析方法與工具結果。
3. 將資料中的直接觀察、模型預測與需要補查的原因假設分開呈現。
4. 分開測試一般問題與資料不足／模糊時間／設備不可辨識等情況。
5. 以同一模型有無外部回答檢查與修正作對照；具體配置見 [分析方法與評估計畫](06_methods_and_evaluation.md)。

## 6. 核對紀錄與適用界線

- [1] 已核對報告住宅相關正文及 PDF 第 25 頁圖表；全文抽取已存 references/D1/fulltext_pdf.txt。報告頁碼與 PDF 頁序本段一致。
- [2] 已核對作者、摘要、樣本與研究設計、結論，以及問卷自我選擇說明；不是本專題的行為成效承諾。
- [3] 已核對原始 XML 的樣本、介入設計與 Discussion；140 戶為分析樣本，不是最初招募數。
- [4] 引用 arXiv v1，2025-12-31；核對方法、資料與評估／討論段落。不是已確認正式期刊出版的引用。
- [5] 引用 arXiv v2，2026-07-28；已核對新版五位作者、五個模型後端、結論與第 6.3 節限制。v1 仍保留供追溯，不再當成目前唯一版本。HTML 的期刊名稱標頭不足以證明已正式出版，暫按 arXiv 版本引用。
- [6] 已核對 XML 的 Dataset、Results and evaluation、Table 2 與 Conclusion；摘要中的 R² = 0.9745 對應表中 BE06，不是所有站點的整體成績，本提案不將其泛化。
- 未完成所有補充資料與分析程式的重現；目前完成的是原文相關段落核對，沒有宣稱重現研究結果。
- 各篇完整書目及原文路徑見下列參考資料；BibTeX 見 references/references.bib。

## 7. References

[1] International Energy Agency. (2025). *Energy Efficiency 2025*. Published 20 November 2025. [官方報告](https://www.iea.org/reports/energy-efficiency-2025)；[住宅／建築章節](https://www.iea.org/reports/energy-efficiency-2025/buildings)。本機：references/D1/report.pdf。

[2] Boomsma, M., Vringer, K., & van Soest, D. (2025). The impact of real-time energy consumption feedback on residential gas and electricity usage. *Journal of Environmental Economics and Management, 132*, 103163. [DOI](https://doi.org/10.1016/j.jeem.2025.103163)。本機：references/D2/paper.pdf。

[3] Paunov, Y., Grüne-Yanoff, T., Marchionni, C., & Schwirplies, C. (2026). A randomized field experiment comparing nudges and boosts for household electricity conservation in student housing. *Scientific Reports, 16*, 27689. [DOI](https://doi.org/10.1038/s41598-026-69386-6)。本機：references/D3/fulltext.xml、fulltext.txt。

[4] He, T., & Jazizadeh, F. (2025). Context-aware LLM-based AI Agents for Human-centered Energy Management Systems in Smart Buildings. *arXiv:2512.25055v1*. [固定版本](https://arxiv.org/abs/2512.25055v1)。本機：references/A1/paper.pdf、fulltext.html。

[5] Jonah, S., Moses, Q., Babatunde, A., Ajao-Olarinoye, M., & Bammeke, D. (2026). LLMs for Agentic Home Energy Management. *arXiv:2607.04569v2*. [固定版本](https://arxiv.org/abs/2607.04569v2)。本機：references/A2/paper_v2.pdf、fulltext_v2.html。

[6] Muqtadir, A., Li, B., Ying, Z., Songsong, C., & Kazmi, S. N. (2025). Nowcasting the next hour of residential load using boosting ensemble machines. *Scientific Reports, 15*, 7157. [DOI](https://doi.org/10.1038/s41598-025-91767-6)。本機：references/A3/fulltext.xml、fulltext.txt。作者名依原始 XML／出版社資料呈現。

[7] Hebrail, G., & Berard, A. (2006). *Individual Household Electric Power Consumption* [Dataset]. UCI Machine Learning Repository. [DOI](https://doi.org/10.24432/C58K54)。本機：references/DATA1/page.html。此處為資料來源，不列入六筆核心研究的 AI／領域比例。

## 8. Deep Research 補充文獻

以下兩筆支援後續專業取捨討論；加計後為四筆能源領域來源、四篇 AI 技術研究，資料集說明另計。2024 年資料作方法背景，近期動機仍以 2025–2026 年證據為主。

| Ref. | Year | Problem | AI Method | Domain Knowledge | Dataset | Findings | Limitation |
|---|---|---|---|---|---|---|---|
| [8] IEA | 2025 | 需求彈性如何改善電力系統運作？ | 不適用；官方政策與系統分析 | 負載轉移、削峰、系統效率、成本與使用需求 | IEA 系統與案例分析 | 調整用電時點／數量可帶來系統效益；須與能源效率整合 | 本案適用範圍：系統效益不是單戶已量測成效，不能保證移時會降低該戶總電量或費用 |
| [9] Béraud et al. | 2024 | 家庭能源估計如何兼顧誤差、透明度及商業一致性？ | Gradient Boost、Random Forest、線性迴歸、自訂決策樹等比較 | 年用電估計、住房特徵、帳單預估及異常客群 | papernest 約 42,000 客戶；以至少 70 天讀值推估年用電 | 作者選用可解釋自訂樹，並指出異常客群的韌性問題；RF 在原文比較中表現較佳 | 年用電／新客戶估計，不是本案下一小時預測；資料為企業客戶，不能直接比較分數；arXiv v1 |

[8] International Energy Agency. (2025). *The Value of Demand Flexibility: Benefits beyond balancing*. Published 23 December 2025. [官方來源](https://www.iea.org/reports/the-value-of-demand-flexibility)。本機：references/D5/report.pdf。核對摘要與需求彈性／效率相關段落。

[9] Béraud, P., Rioux, M., Babany, M., de La Chevasnerie, P., Theis, D., Teodori, G., Pinguet, C., Rigaud, R., & Leclerc, F. (2024). An explainable machine learning approach for energy forecasting at the household level. *arXiv:2410.14416v1*. [固定版本](https://arxiv.org/abs/2410.14416v1)。本機：references/A4/paper.pdf、fulltext.html。核對 Methodology、Results 與 Conclusion；正式期刊出版未確認。
