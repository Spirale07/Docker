FROM ruby:2.4

ENV NAME=ft-rails

RUN apt-get update && apt-get install -y sqlite3 \
	nodejs \
	git \
	build-essential \
	libpq-dev \
	postgresql-client \
	postgresql \
	libxslt1-dev \
	libqt4-webkit \
	libqt4-dev \
	xvfb \
	redis-server

ENV APP_PATH /opt/app
RUN mkdir -p APP_PATH
WORKDIR $APP_PATH

COPY Gemfile* $APP_PATH/
RUN bundle install

COPY . .

RUN if rails new $APP_PATH; \
	then echo "GOOD"; \
	else rake db:create && rake db:migrate; \
	fi