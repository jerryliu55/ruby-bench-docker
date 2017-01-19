FROM rubybench/ruby:0.3

# branch is temporary (should be master)
# repo is temporary (should be ruby-bench/ruby-bench-suite)
RUN git clone --verbose --branch submodule-liquid --single-branch https://github.com/jerryliu55/ruby-bench-suite.git

# branch is temporary (should be master)
# RUN git clone --verbose --branch benchmark-render --single-branch https://github.com/shopify/liquid.git

# gems
# RUN /bin/bash -l -c "gem install liquid benchmark-ips --no-ri --no-rdoc"

ADD runner runner
RUN chmod 755 runner

CMD /bin/bash -l -c "./runner"
