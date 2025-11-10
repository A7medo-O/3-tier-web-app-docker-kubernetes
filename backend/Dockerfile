# builder stage
FROM golang:1.21 AS builder
WORKDIR /app
# cache modules
COPY go.mod go.sum ./
RUN go mod download

# copy source and build
COPY . .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o /app/main .

# final minimal image
FROM gcr.io/distroless/static:nonroot
WORKDIR /app
COPY --from=builder /app/main /app/main
# nonroot user is already used by distroless; ensure port exposed for docs
EXPOSE 8080
ENTRYPOINT ["/app/main"]

