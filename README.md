# 🌵 サボテン管理アプリ

Webブラウザ上で完結するサボテン管理アプリケーションです。複数のサボテンを管理し、環境条件をモニタリングして最適な育成環境を維持できます。

## ✨ 特徴

- 🌵 **複数サボテン管理**: 1つのアプリで複数のサボテンを管理
- 📸 **写真管理**: サボテンの写真をアップロード・表示
- 🌡️ **環境監視**: 気温・湿度を監視し、最適範囲との比較
- 🔔 **通知機能**: 環境が最適範囲を外れた場合の自動通知
- 📱 **レスポンシブ**: モバイル・デスクトップ対応
- 🎨 **モダンUI**: 美しいグラデーションとアニメーション

## 🚀 デモ

[🌵 アプリを試す](https://your-username.github.io/cactus-manager-app/)

## 📋 管理項目

各サボテンについて以下の情報を管理できます：

- サボテンの名前
- サボテンの種類（エキノカクタス、マミラリア等）
- サボテンの写真
- 水やり頻度
- 最適温度
- 最適湿度

## 🛠️ 技術仕様

- **フロントエンド**: HTML5, CSS3, Vanilla JavaScript
- **スタイリング**: CSS Grid, Flexbox, グラデーション
- **レスポンシブ**: モバイルファースト設計
- **ファイル構成**: 単一HTMLファイル（依存関係なし）

## 💻 ローカル開発

1. リポジトリをクローン:
```bash
git clone https://github.com/your-username/cactus-manager-app.git
cd cactus-manager-app
```

2. ブラウザでindex.htmlを開く、または簡易サーバーを起動:
```bash
# Python 3の場合
python -m http.server 8000

# Node.jsの場合
npx serve .
```

3. ブラウザで `http://localhost:8000` にアクセス

## 🔧 カスタマイズ

### 気象APIの統合

現在はダミーデータを使用していますが、実際の気象データを取得したい場合：

1. [OpenWeatherMap](https://openweathermap.org/api) でAPIキーを取得
2. `fetchWeatherData()` 関数を以下のように修正:

```javascript
async function fetchWeatherData() {
    try {
        const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=Yokohama&appid=YOUR_API_KEY&units=metric`);
        const data = await response.json();
        currentWeather = {
            temperature: Math.round(data.main.temp),
            humidity: data.main.humidity
        };
        updateWeatherDisplay();
        checkAllCactiConditions();
    } catch (error) {
        console.error('気象データの取得に失敗:', error);
    }
}
```

### サボテン種類の追加

`species` セレクトボックスに新しい種類を追加できます：

```html
<option value="新しい種類">新しい種類</option>
```

## 📱 PWA対応

PWA（Progressive Web App）として使用したい場合は、以下のファイルを追加：

- `manifest.json`: アプリマニフェスト
- `sw.js`: サービスワーカー
- アイコンファイル群

## 🤝 コントリビューション

1. このリポジトリをフォーク
2. 新しいブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add some amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

## 📄 ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細は [LICENSE](LICENSE) ファイルを参照してください。

## 🐛 バグ報告・機能要望

バグ報告や機能要望は [Issues](https://github.com/your-username/cactus-manager-app/issues) からお願いします。

## 📞 お問い合わせ

プロジェクトについてのご質問は以下まで：

- GitHub: [@your-username](https://github.com/your-username)
- Email: your-email@example.com

---

⭐ このプロジェクトが役に立った場合は、スターをつけていただけると嬉しいです！
