Thumbnail Generator using AWS

Features
- Upload image through a simple web UI
- Automatically generate thumbnail
- Download thumbnail from the UI
- Progress indication during processing
- Secure and scalable serverless architecture

Architecture Overview
1. User selects an image from the browser.
2. Frontend requests a **pre-signed URL** from API Gateway.
3. AWS Lambda generates the pre-signed URL.
4. Browser uploads the image **directly to Amazon S3**.
5. S3 triggers a Lambda function.
6. Lambda generates a thumbnail using Python.
7. Thumbnail is stored back in S3.
8. User downloads the generated thumbnail.

[Browser (localhost)]
        |
        | fetch()
        v
[API Gateway]
        |
        v
[Lambda: get presigned URL]
        |
        v
[Browser uploads image]
        |
        v
[S3 bucket]
        |
        v
[Lambda: thumbnail generator]
        |
        v
[S3 (thumbnail)]