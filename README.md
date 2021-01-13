# story-analysis-localstack

https://dev.to/vikasgarghb/sam-local-with-localstack-4285                


Install

pip3 install localstack-client

1. Start the docker container

docker-compose up -d

2. Create test bucket in the container and print the configuration

docker exec -it localstack /bin/bash
awslocal s3 mb s3://story-analysis-rc
cat /tmp/localstack/data/recorded_api_calls.json

3. Copy the configuration and put it in localstack/data/recorded_api_calls.js


4. Check access inside the container or in host as follows. 

aws --endpoint-url=http://localhost:4566 s3 ls s3://story-analysis-rc


5. Connet it to local sam network

docker network connect sam-net-story-survey-api localstack