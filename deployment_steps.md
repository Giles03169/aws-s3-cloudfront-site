# AWS S3 Static Website Deployment — Step-by-Step

## 1. Create the Bucket
- Bucket name: `my-static-site-giles`
- Region: `eu-west-1`
- Disabled "Block all public access"

## 2. Upload Files
- `index.html` and `error.html` uploaded to bucket root

## 3. Enable Static Hosting
- Properties → Static website hosting
- Index document: `index.html`
- Error document: `error.html`

## 4. Set Bucket Policy
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadForStaticWebsite",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-static-site-giles/*"
    }
  ]
}
