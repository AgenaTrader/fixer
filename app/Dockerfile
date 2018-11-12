FROM ruby:2.5.0

RUN mkdir /app

WORKDIR /app

ADD . /app

RUN cd gem && gem build fixer.gemspec
RUN bundle install --jobs=8 --without development

CMD ["unicorn", "-c", "./config/unicorn.rb"]
