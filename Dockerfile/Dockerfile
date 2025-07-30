# ビルドステージ
FROM golang:alpine AS builder

# 作業ディレクトリ作成
WORKDIR /app

# Goファイルをコンテナにコピー
COPY main.go .

# Goプログラムをビルド（静的リンクにする）
RUN go build -o main main.go

# 実行ステージ（軽量）
FROM alpine

# ビルド済みバイナリをコピー
COPY --from=builder /app/main .

# 実行コマンド
CMD ["./main"]
