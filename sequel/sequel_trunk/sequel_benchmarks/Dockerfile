FROM rubybench/ruby:0.4
MAINTAINER Alan Guo Xiang Tan "https://twitter.com/tgx_world"

RUN apt-get update
RUN apt-get install -y libncurses5-dev libmysqlclient-dev postgresql mysql-server-5.6

RUN git clone --verbose --branch master --single-branch https://github.com/ruby-bench/ruby-bench-suite.git
RUN git clone --verbose --branch master --single-branch https://github.com/jeremyevans/sequel.git
RUN /bin/bash -l -c "gem install bundler --no-ri --no-rdoc && cd /sequel && bundle install --without test doc job"

ADD runner runner
RUN chmod 755 runner

CMD /bin/bash -l -c "./runner"
