# News Articles Search Engine

## Project Description
This project periodically import news articles crawled from the internet by the [Common Crawl](https://commoncrawl.org/the-data/). The imported new articles are searchable with keywords (highlighted in returned results in pages), publishing date, and language (English and Non-English).

This project consists 4 parts:
1. A [AWS Lambda](https://aws.amazon.com/lambda/) function that periodically imports (checking every hour) the latest crawled news articles and sends parsed news to [AWS Simple Queue Service (SQS)](https://aws.amazon.com/sqs/)
2. A AWS Lambda function that retrieves parsed news from AWS SQS and post them to [AWS Elasticsearch Service](https://aws.amazon.com/elasticsearch-service/)
3. Backend Search API
4. Frontend Search Website

When posting articles to AWS Elasticsearch serivce, the news HTML webpages collectively stored in a `.warc.gz` file is each parsed to the following fields in a JSON Object:
- URL
- Title
- Text
- Language
- Publishing Date

The backend Search API is deployed to an [Apache Tomcat](https://en.wikipedia.org/wiki/Apache_Tomcat) environment managed by [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/). The frontend Search website is hosted in a [AWS S3](https://aws.amazon.com/s3/) bucket.

The complete code base is available upon request due to academic integrity policy. A video that describes the project is available [here](https://youtu.be/HTkAXr3fQCE).
