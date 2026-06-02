# Git/GitHub 勉強会リポジトリ

## ハンズオン手順

### 1. リポジトリをクローン
```bash
git clone <リポジトリURL>
cd git-study-session
```

### 2. ブランチを作成
```bash
git checkout -b <自分の名前（例: kjokei）>
```

### 3. テンプレートをコピー
```bash
cp template.go students/<自分のブランチ名>.go
```

例: ブランチ名が `kjokei` の場合
```bash
cp template.go students/kjokei.go
```

### 4. ファイルを編集

`students/<自分のブランチ名>.go` をエディタで開き、`"YOUR_BRANCH_NAME"` を自分のブランチ名に書き換えてください。

```go
fmt.Println("kjokei")  // ← ここを自分のブランチ名に変更
```

### 5. コミット＆プッシュ
```bash
git add .
git commit -m "Add my go file"
git push origin <自分のブランチ名>
```

### 6. Pull Request を作成

GitHub 上でブランチを選択し、`main` ブランチへの Pull Request を作成してください。

### 7. CI の確認

Pull Request を作成すると自動でCIが実行されます。  
「All checks have passed ✅」が表示されれば成功です！
