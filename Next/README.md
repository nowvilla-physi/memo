# Next.jsに関するメモ

## 環境構築
以下に環境構築の手順を記載する。

### Next.jsのプロジェクトの作成
`npx create-next-app <project>`を実行する。  
`yarn dev`を実行し、`http://localhost:3000`にアクセスできることを確認する。

### プロジェクトフォルダのフォルダ構成の定義
以下のコマンで`src`ディレクトリを作成し、`pages`ディレクトリと`styles`ディレクトリを`src`ディレクトリに移動する。  
`mkdir src && mv pages src && mv styles src`

### TypeScriptの導入
以下のコマンドを実行する。  
`npm install --save-dev typescript @types/react @types/react-dom`

以下のファイルをリネームする。
- `_app.jsx` -> `_app.tsx`  
- `index.js` -> `index.tsx`

[tsxの中身はこれを参考にする](https://github.com/nowvilla-physi/Memo/tree/main/Next/templates/pages)

### Sassの導入
以下のコマンドを実行する。  
`npm install sass --save-dev`  

以下のファイルをリネームする。
- `global.css` -> `global.scss`
- `Home.module.css` -> `Home.module.scss`

[scssの中身はこれを参考にする](https://github.com/nowvilla-physi/Memo/tree/main/Next/templates/scss)

### tsconfig.jsonの作成
`yarn dev`を実行すると、`tsconfig.json`が作成される。

### eslintの導入
以下のコマンドを実行する。  
`npx eslint --init`  
色々聞かれる。  
[.eslintrc.jsの中身はこれを参考にする](https://github.com/nowvilla-physi/Memo/blob/main/Next/templates/.eslintrc.js)

### prettierの導入
以下のコマンドを実行する。  
`npm install ---save-dev prettier eslint-config-prettier eslint-plugin-prettier`  
[.prettierrc.jsonの中身はこれを参考にする](https://github.com/nowvilla-physi/Memo/blob/main/Next/templates/.prettierrc.json)

### リントのかけ方
- フォーマットが崩れているところを洗い出すコマンドは以下。
    - `npx eslint . --ext .tsx --ext .ts`
- フォーマットが崩れているところを修正するコマンドは以下。
    - `npx eslint . --ext .tsx --ext .ts --fix`

### .gitignoreの追加
[.gitignoreの中身はこれを参考にする](https://github.com/nowvilla-physi/Memo/blob/main/Next/templates/.gitignore)
