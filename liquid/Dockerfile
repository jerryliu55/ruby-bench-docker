FROM rubybench/ruby:0.3

# branch is temporary (should be master)
# repo is temporary (should be ruby-bench/ruby-bench-suite)
RUN git clone --verbose --branch liquid-test --single-branch https://github.com/jerryliu55/ruby-bench-suite.git

# branch is temporary (should be master)
RUN git clone --verbose --branch benchmark-render --single-branch https://github.com/shopify/liquid.git

# move some liquid/performance files to bench-suite
# RUN mv /liquid/performance/tests      /ruby-bench-suite/liquid/benchmarks/support && \
#   rm /liquid/performance/shopify/liquid.rb && \
#   mv /liquid/performance/shopify/* /ruby-bench-suite/liquid/benchmarks/support/shopify && \
#   mv /liquid/performance/theme_runner.rb /ruby-bench-suite/liquid/benchmarks/support

# gems
RUN /bin/bash -l -c "gem install liquid benchmark-ips --no-ri --no-rdoc"

ADD runner runner
RUN chmod 755 runner

ENTRYPOINT ["/bin/bash", "-lc", "./runner"]
