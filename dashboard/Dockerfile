FROM ruby:2.3.3

ENV APP_HOME="/myapp" 
RUN apt-get update -qq \
	&& apt-get install -y \
		build-essential \
		libpq-dev \
		libqt4-webkit \
		libqt4-dev \
		xvfb \
		nodejs \
	&& apt-get clean autoclean \
	&& apt-get autoremove -y \
	&& rm -rf \
		/var/lib/apt \
		/var/lib/dpkg \
		/var/lib/cache \
		/var/lib/log
RUN mkdir $APP_HOME
WORKDIR $APP_HOME

ADD Gemfile* $APP_HOME/
RUN bundle install

ADD . $APP_HOME

