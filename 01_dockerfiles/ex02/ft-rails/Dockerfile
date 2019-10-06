FROM ruby:latest
RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3 gem
RUN gem install bundler --no-document
RUN gem install rails --no-document
RUN gem install rake -v 12.3.1 --no-document
LABEL maintainer="taethan@student.21-school.ru"

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake _12.3.1_ db:migrate
ONBUILD RUN rake _12.3.1_ db:seed
ONBUILD RUN rake _12.3.1_

# docker build -t ft-rails:on-build .

# https://bitbucket.org/railstutorial/sample_app_4th_ed/src/master/
# docker build -t ft-rails:on-build .       - Создайте образ из вашего Dockerfile
# docker build -t ex02 .                    - Создайте образ из Dockerfile, предоставленного задачей
# docker run -it --rm -p 3000:3000 ex02     - запустить созданное изображение