# Stage 1: build application
# Use golang 1.13.5 image based alpine 3.10
FROM golang:1.13.5-alpine3.10 as builder
# Copy main.go file to container on the build machine
COPY ./main.go ./
# run this command inside the container when it's built
RUN go build -o /go-app ./main.go


# Stage 2: create container included binary file from stage 1
FROM alpine:3.7
# expose port 8080
EXPOSE 8080
# execution user as nobody
COPY --from=builder /go-app .

# When container boots, run following command
ENTRYPOINT ["./go-app"]
