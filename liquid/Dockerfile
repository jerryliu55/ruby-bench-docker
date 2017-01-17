FROM rubybench/ruby:0.3

# branch is temporary (should be master)
RUN git clone --verbose --branch benchmark-render --single-branch https://github.com/shopify/liquid.git

# branch is temporary (should be master)
# repo is temporary (should be ruby-bench/ruby-bench-suite)
RUN git clone --verbose --branch liquid-test --single-branch https://github.com/jerryliu55/ruby-bench-suite.git

# move some liquid/performance files to bench-suite
RUN mv /liquid/performance/tests /ruby-bench-suite/liquid/benchmarks/support
RUN rm /liquid/performance/shopify/liquid.rb
RUN mv /liquid/performance/shopify/* /ruby-bench-suite/liquid/benchmarks/support/shopify
RUN mv /liquid/performance/theme_runner.rb /ruby-bench-suite/liquid/benchmarks/support

ADD runner runner
RUN chmod 755 runner

CMD /bin/bash -l -c "./runner"
