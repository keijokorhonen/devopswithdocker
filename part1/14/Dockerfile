FROM ruby:2.6.0

EXPOSE 3000
RUN apt-get update && apt-get install -y git curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
RUN npm install
RUN gem install bundler
RUN git clone https://github.com/docker-hy/rails-example-project.git
WORKDIR /rails-example-project
RUN bundle install
RUN rails db:migrate
CMD rails s
