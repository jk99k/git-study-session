# Git/GitHub 勉強会リポジトリ

## ハンズオン手順

### 1. リポジトリをクローン
```bash
git clone <リポジトリURL>
cd git-study-session
```

### 2. ブランチを作成
```bash
git checkout -b <自分の名前（例: goura）>
```

### 3. テンプレートをコピー
```bash
cp template.go students/<自分のブランチ名>.go
```

例: ブランチ名が `goura` の場合
```bash
cp template.go students/goura.go
```

### 4. ファイルを編集

`students/<自分のブランチ名>.go` をエディタで開き、`"YOUR_BRANCH_NAME"` を自分のブランチ名に書き換えてください。

```go
fmt.Println("goura")  // ← ここを自分のブランチ名に変更
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

## 8. リポジトリ構成

```
git-study-session/
├── .github/
│   └── workflows/
│       └── check-branch-name.yml  # CI設定 (Pull Request時に自動実行)
├── students/                       # 生徒が自分のGoファイルを置くディレクトリ
├── template.go                     # 生徒がコピーして使うテンプレート
└── README.md                       # この手順書
```

### 各ファイルの役割

- **`template.go`**: ハンズオンの出発点。`fmt.Println("YOUR_BRANCH_NAME")` の1行だけ書き換えて `students/` にコピーして使う。
- **`students/`**: 全員のGoファイルが集まるディレクトリ。ファイル名はブランチ名と同じにする（例: `taro-yamada.go`）。
- **`.github/workflows/check-branch-name.yml`**: Pull Requestが作成されると自動で以下の2点をチェックするCI。
  1. `students/<ブランチ名>.go` が存在するか
  2. そのファイルを実行した出力がブランチ名と一致するか
