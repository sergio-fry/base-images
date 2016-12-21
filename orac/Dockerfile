FROM ruby:2.2.5

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

COPY .docker/phantomjs-2.1.1-linux-x86_64.tar.bz2 /
RUN tar -xvf /phantomjs-2.1.1-linux-x86_64.tar.bz2
RUN ln -s /phantomjs-2.1.1-linux-x86_64/bin/phantomjs /usr/bin/phantomjs

# Deploy tool setup
RUN gem i dpl -v '1.8.24'

RUN mkdir /app
WORKDIR /app

COPY Gemfile* /app/
RUN bundle install
