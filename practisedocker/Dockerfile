# Pythonの公式イメージをベースにする（バージョンは必要に応じて変更）
FROM python:3.9-slim

# 作業ディレクトリを/appに設定
WORKDIR /app

# 必要なファイル（requirements.txt）をコンテナ内にコピー
COPY requirements.txt /app/

# 依存関係をインストール
RUN pip install --no-cache-dir -r requirements.txt

# プロジェクトのソースコードをコンテナ内にコピー
COPY . /app/

# Djangoのマイグレーションを実行（データベースを準備）
RUN python manage.py migrate

# コンテナ起動時にDjango開発サーバーを起動
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# ポート8000を公開
EXPOSE 8000
