# Docker LOGSTASH RSPEC Unit Test Environment

## Usgae

1. Start test environmenmt
    docker-compose up -d --build
2. Execute test
    docker exec -it dockerlogstash_logstash_1 /logstash/bin/rspec /logstash/test/spec/02_filter_spec.rb