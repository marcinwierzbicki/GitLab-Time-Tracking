FROM ruby:2.3

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        postgresql-client \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app
COPY Gemfile* ./
RUN bundle install
COPY . .
EXPOSE 9292
CMD ["bundle", "exec", "rackup", "--host", "0.0.0.0", "-p", "9292"]
