# 概要
FastAPIをvercel上までホスティングするまでの流れと、サンプルデータです。

#### テンプレートを使って、とりあえずデプロイしたい方

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/git?s=https://github.com/testkun08080/FastAPI-vercel)

#### サンプルページ
https://fast-api-vercel-murex.vercel.app/

## 事前インストール必要なもの

- Python 3.12 (vercelの最新が3.12対応のため - 2025/6/3)
- uv (インストールは[こちら](https://docs.astral.sh/uv/getting-started/installation/))
- Vercel CLI (インストールは[こちら](https://vercel.com/docs/cli#installing-vercel-cli/))

## ローカル上でセットアップから起動

1. **ローカルへクローンする**
    ```bash
    git clone https://github.com/testkun08080/FastAPI-vercel.git
   ```

3. **仮想環境の構築**
    ```bash
    cd FastAPI-vercel
    uv venv -p 3.12
    uv pip install -r requirements.txt
   ```
   
4. **起動**
    ```bash
    uv run -m api.app.main
   ```

## Pytestを使ったテスト
1. **テスト用にモジュールをインストール**
    ```bash
    uv pip install -r requirements_test.txt
   ```
1. **Pytest実行**
    ```bash
    uv run pytest --html=report.html --self-contained-html --log-level=INFO
   ```

## Vercel CLI を使ってテストからデプロイ/ホスティングまで

1. **ローカルでテスト**
    ```bash
    vercel dev
   ```

2. **vercelへデプロイ（プレビューとして）**
    ```bash
    vercel
   ```

3. **、vercelへデプロイ（プロダクトとして）**
    ```bash
    vercel --prod
   ```