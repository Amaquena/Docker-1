FROM ruby:2.6.2

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3 gem

RUN gem install rails
RUN gem install bundler
RUN gem install rake

ONBUILD COPY ruby-docs-hello-world /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD EXPOSE 3000
ONBUILD RUN bundle update --bundler
ONBUILD RUN bundle install
ONBUILD RUN rake _12.3.2_ db:migrate
ONBUILD RUN rake _12.3.2_ db:seed
ONBUILD RUN rake _12.3.2_