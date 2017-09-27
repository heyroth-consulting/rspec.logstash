# Docker LOGSTASH RSPEC Unit Test Environment

## Usage

1. Start test environmenmt
    `docker-compose up -d --build`
2. Execute test via command line
    `docker exec -it rspeclogstash_logstash_1 /logstash/bin/rspec /logstash/test/spec/02_filter_spec.rb`
3. To execute multiple tests at once
    `docker exec -it rspeclogstash_logstash_1 /logstash/bin/rspec -P '/logstash/test/spec/*_spec.rb'`
4. To generate an output for the test results add the following to the command
    `--format html --out /logstash/test/output/rspec_results.html`
5. Execute test via Maven
    `mvn clean integration-test`
6. Execute with docker build info
    `mvn package -D docker.verbose=true`
