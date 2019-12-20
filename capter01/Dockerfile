# Use golang 1.13.5 image based alpine 3.10
FROM golang:1.13.5-alpine3.10

# expose port 8080
EXPOSE 8080

# Copy main.go file to container on the build machine
COPY ./main.go ./

# run this command inside the container when it's built
RUN go build -o ./go-app ./main.go

# execution user as nobody
USER nobody

# When container boots, run following command
ENTRYPOINT ["./go-app"]
