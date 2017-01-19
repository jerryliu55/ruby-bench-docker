FROM rubybench/ruby:0.3

# branch is temporary (should be master)
# repo is temporary (should be ruby-bench/ruby-bench-suite)
RUN git clone --verbose --branch submodule-liquid --single-branch https://github.com/jerryliu55/ruby-bench-suite.git

RUN git clone --verbose --branch trunk --single-branch https://github.com/ruby/ruby.git

ADD runner runner
RUN chmod 755 runner

CMD /bin/bash -l -c "./runner"
