# SQS

### Amazon SQS Standard queues
- the default queue type
- nearly unlimited number of API calls per second, per API action
- more than one copy of a message might be delivered out of order

### FIFO queues (first-in-first-out)
- FIFO is used where duplicates can't be tolerated
- have a limited number of transactions per second (TPS)
- support up to 3,000 transactions per second, per API method (300 API calls * 10 batching messages)
- https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html
