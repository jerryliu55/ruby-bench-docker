## Discourse Benchmarks

#### Build base image for Discourse
```bash
cd discourse_benchmarks
sudo docker build --no-cache -t tgxworld/discourse_bench .
```

#### Setup containers for Redis server and PostgreSQL
```bash
sudo docker run --name discourse_redis -d redis && sudo docker run --name discourse_postgres -d postgres
```

#### Run Discourse benchmarks
```bash
sudo docker run --rm --name discourse_benchmarks --link discourse_postgres:postgres --link discourse_redis:redis -e "RAILS_COMMIT_HASH=<hash to benchmark against>" -e "RUBY_VERSION=2.1.5" tgxworld/discourse_bench
```

## Ruby Benchmarks

#### Build base image for Ruby benchmarks
```bash
sudo docker build --no-cache -t tgxworld/ruby_bench .
```

#### Run Ruby benchmarks
```bash
sudo docker run --rm --name ruby_benchmarks -e "RUBY_VERSION=2.1.5" tgxworld/ruby_bench
```
