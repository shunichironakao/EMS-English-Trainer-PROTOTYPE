# EMS English Trainer [PROTOTYPE]

救急英語スピーキングトレーナー — コーパス分析に基づく救急隊員向け英語発話練習アプリ

🔗 **アンケートあり版はこちら**: [ems-english-trainer-survey](https://github.com/shunichironakao/ems-english-trainer-survey)

---

## 概要

本アプリは、救急現場で外国語対応が必要な救急隊員を対象とした、英語スピーキング練習ツールです。コーパス言語学の手法（共起分析・Effectスコア）で選出した、臨床的根拠のある英語表現を、Web Speech APIによるリアルタイム音声認識で練習できます。

## 主な機能

- 🎤 **音声認識**：Web Speech APIによるリアルタイム認識（完全一致不要・キーワードマッチング）
- 🔊 **患者返答の音声合成**：認識成功後、北米英語音声（Samantha / Zira等）で患者役AIが返答
- 🔤 **単語別フィードバック**：発話後、各単語の認識可否を緑（✓）・赤（✗）で即時表示
- 📈 **苦手単語の自動集計**：完了画面でセッション中の未認識単語をバーグラフで表示
- 📊 **根拠に基づく表現選出**：各表現にEffectスコアと出現頻度を表示
- 🏥 **10症候対応**：救急現場で頻度の高い10症候をカバー
- 📋 **8フェーズ構成**：初期接触から搬送告知まで現場の流れを再現
- 📱 **レスポンシブ対応**：PC・タブレット・スマートフォン（Android/Chrome）で動作

## 対応症候

| # | 症候（日本語） | Chief Complaint |
|---|---|---|
| 1 | 胸痛 | Chest Pain 🫀 |
| 2 | 呼吸困難 | Respiratory Distress 🫁 |
| 3 | めまい | Dizziness 💫 |
| 4 | 頭痛 | Headache 🧠 |
| 5 | 背部痛 | Back Pain 🦴 |
| 6 | 意識障害 | Altered Consciousness 🧍 |
| 7 | 腹痛 | Abdominal Pain 🫃 |
| 8 | 嘔気嘔吐 | Nausea & Vomiting 🤢 |
| 9 | 脱力 | Weakness 💪 |
| 10 | 全身倦怠感 | General Fatigue 😩 |

## トレーニングフェーズ（全症候共通）

各症候につき以下の8フェーズを順番に練習します：

1. **Initial Contact** — 初期接触
2. **Chief Complaint** — 主訴聴取
3. **Pain Assessment** — 痛み評価
4. **SAMPLE History** — 病歴聴取
5. **Physical Assessment** — 身体評価
6. **Instructions** — 指示
7. **Reassurance** — 安心づけ
8. **Transport** — 搬送

## 使用技術

| 技術 | 用途 |
|---|---|
| Web Speech API（SpeechRecognition） | リアルタイム音声認識 |
| Web Speech API（SpeechSynthesis） | 患者役音声合成 |
| Levenshtein距離（公開アルゴリズム, 1965） | 単語のファジーマッチング |
| HTML / CSS / Vanilla JavaScript | フロントエンド全般 |

**推奨ブラウザ**：Google Chrome または Microsoft Edge（Web Speech API対応）

## 表現選出の言語学的根拠

- 10症候 × 20シナリオ = **200スクリプト**（延べ語数 約41,962語）のコーパスを独自構築
- 共起分析により **Effect = log₂(観測値 / 期待値) ≥ 2.0** の表現を選出
- 文部科学省中学校英語語彙リストに準拠した語彙レベル制限
- 原則 **1文・8語以内** に整理し、臨床現場での即時発話を優先

## プライバシー

本アプリはすべてブラウザ上で動作します。音声データ・入力データはサーバーへ送信されず、外部に保存されません。

## 作成者

**Shunichiro Nakao, MD, MSc, PhD**

**Department of Traumatology and Acute Critical Medicine, The University of Osaka**

This project was supported by a grant from The Mitsubishi Foundation.

## ライセンス

本アプリのコードは研究・教育目的での使用を想定しています。
Levenshtein距離アルゴリズムはパブリックドメイン（V.I. Levenshtein, 1965）です。
