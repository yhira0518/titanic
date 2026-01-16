タイタニック号の乗客データに基づき、生存者を予測する機械学習プロジェクトです。


## 📊 プロジェクトの成果
- **最終スコア**: 約 84%〜85% (Test Accuracy)
- **主要アルゴリズム**: XGBoost, LightGBM, Random Forest

## 💡 こだわったポイント
このプロジェクトでは、単なるモデルの適用だけでなく、以下のデータ加工（特徴量エンジニアリング）に注力しました。

1. **敬称の抽出 (Title Extraction)**:
   - 名前列から "Mr", "Miss", "Master" などの敬称を抽出し、社会的ステータスをモデルに反映。
2. **家族情報の統合 (Family Engineering)**:
   - `SibSp` と `Parch` を統合して `FamilySize` を作成。さらに「一人旅かどうか（IsAlone）」のフラグを追加。
3. **年齢のビン詰め (Age Binning)**:
   - 年齢を5つのグループにカテゴリ化し、細かいノイズを排除してモデルの安定性を向上。
4. **アンサンブル学習 (Voting)**:
   - 特性の異なる3つのモデル（XGBoost, LightGBM, Random Forest）による「Soft Voting」を採用し、単体モデルの弱点を補完。
