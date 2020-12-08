FROM ruby

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt update && apt -y upgrade
RUN apt install -y sqlite3 nodejs
RUN install --no-install-recommends yarn
RUN gem install rails bundler
# ONBUILD WORKDIR /opt/app
# # ONBUILD ADD Gemfile Gemfile.lock ./
# ONBUILD ADD . .
# ONBUILD RUN bundle install

WORKDIR /opt/app
# ADD Gemfile ./Gemfile
# ADD Gemfile.lock ./Gemfile.lock
ADD . .
RUN bundle install
# RUN bundle update
RUN rails webpacker:install
CMD [ "rails", "s", "-b", "0.0.0.0", "-p", "3000" ]