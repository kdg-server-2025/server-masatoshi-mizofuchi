# ===== ビルドステージ =====
FROM golang:1.24-alpine3.22 AS builder

WORKDIR /app
COPY main.go .

RUN go build -o myapp main.go

# ===== 実行ステージ =====
FROM scratch

WORKDIR /

# builder ステージからコンパイル済バイナリのみコピー
COPY --from=builder /app/myapp /myapp

# 実行コマンド
CMD ["/myapp"]
