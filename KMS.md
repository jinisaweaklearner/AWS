## Customer master keys (CMKs)
All activity using a key in a custom key store is also logged to AWS CloudTrail in the same way.
https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html


## SSE Server Side Encryption

- SSE-S3: AWS manages both data key and master key
- SSE-KMS: AWS manages data key and you manage master key
- SSE-C: You manage both data key and master key