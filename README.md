# Docker LOGSTASH RSPEC Unit Test Environment

## Usage

1. Start test environment:

    ```docker-compose up -d --build```
   
2. Execute test via command line:

    ```docker exec -it rspeclogstash_logstash_1 /logstash/bin/rspec /logstash/test/spec/02_filter_spec.rb```
    
3. To execute multiple tests at once:

    ```docker exec -it rspeclogstash_logstash_1 /logstash/bin/rspec -P '/logstash/test/spec/*_spec.rb'```
    
4. To generate an output for the test results add the following to the command:

    ```--format html --out /logstash/test/output/rspec_results.html```
    
6. Create Docker image with Maven:

    ```mvn package -D docker.verbose=true```

5. Execute test via Maven:

    ```mvn clean verify -D docker.verbose=true```
