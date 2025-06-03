# 概要
FastAPIをvercel上までホスティングするまでの流れと、サンプルデータです。


## 事前インストール必要なもの

- Python 3.12+ (vercelの最新が3.12対応のため - 2025/6/3)
- uv (インストールは[こちら](https://docs.astral.sh/uv/getting-started/installation/))
- Vercel CLI (インストールは[こちら](https://vercel.com/docs/cli#installing-vercel-cli/))



## ローカル上でセットアップから起動

1. **仮想環境の構築**
    ```bash
    python3.12 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt
   ```
   
2. **起動**
    ```bash
    uvicorn api.app.main:app --reload 
   ```
   or
    ```bash
    python -m api.app.main
   ```

## Pytestを使ったテスト
1. **テスト用にモジュールをインストール**
    ```bash
    uv pip install -r requirements_test.txt
   ```
1. **Pytest実行**
    ```bash
    pytest --html=report.html --self-contained-html --log-level=INFO
   ```

## Vercel CLI を使ってテストからデプロイ/ホスティングまで

1. **ローカルでテスト**
    ```bash
    vercel dev
   ```

1. **vercelへデプロイしてプレビューとして確認ト**
    ```bash
    vercel
   ```

1. **実際にプロダクトとして、vercelへデプロイ**
    ```bash
    vercel --prod
   ```