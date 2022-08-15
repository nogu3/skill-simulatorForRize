FROM ruby:3.1.2

# set env
ARG homeDir="/home/src"

# -qq=エラー以外表示しない
RUN apt-get update -qq && \
    # 開発に必須のビルドツールを提供しているパッケージ
    apt-get install -y build-essential

# make srcdir
RUN mkdir -p ${homeDir}
WORKDIR ${homeDir}

# Gemfileのコピー
COPY Gemfile ${homeDir}/Gemfile
COPY Gemfile.lock ${homeDir}/Gemfile.lock

RUN bundle install
