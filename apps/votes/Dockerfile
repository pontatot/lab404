FROM dhi.io/golang:1.26-dev@sha256:c1e60bfcf708775a036d8777a4a29b6c26f618bbf639a9a6161559c5adda20af AS build
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 go build -o votes .

FROM scratch
COPY --from=build /app/votes /votes
USER 65532:65532
EXPOSE 8081
ENTRYPOINT ["/votes"]
