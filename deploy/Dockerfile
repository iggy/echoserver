








# FROM golang:1.14-buster AS builder
# RUN apt-get update \
#   && apt-get upgrade -y
# RUN apt-get install -y git make upx
# RUN env
# WORKDIR /app
# COPY . .
# RUN make deps
# RUN make build_production
# RUN make compress

FROM gcr.io/distroless/base-debian10
ARG GIT_COMMIT_ID="undefined"
ARG GIT_TAG="undefined"
ARG BUILD_TIMESTAMP="undefined"
ENV PATH=/bin
# COPY --from=builder /app/bin/echoserver_linux_amd64 /bin/echoserver
COPY ./bin/echoserver_linux_amd64 /bin/echoserver
ENTRYPOINT ["/bin/echoserver"]
# LABEL maintainer "iggy"
# LABEL repository-github "https://github.com/iggy/echoserver"
# LABEL repository_gitlab "https://gitlab.com/usvc/services/echoserver"
# LABEL git_commit_id ${GIT_COMMIT_ID}
# LABEL git_tag ${GIT_TAG}
# LABEL build_timestamp ${BUILD_TIMESTAMP}
