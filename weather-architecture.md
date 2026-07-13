# Architecture

## Request Flow

```
User enters city name
       |
       v
CloudFront CDN (HTTPS)
       |
       v
API Gateway — POST /weather
       |
       v
AWS Lambda (Python 3.12)
       |
       v
OpenWeatherMap API
       |
       v
Weather data processed
       |
       v
JSON response to frontend
```

## AWS Services Used

| Service | Purpose |
|---------|---------|
| AWS Lambda | Serverless function to process requests |
| API Gateway | REST API endpoint |
| OpenWeatherMap API | Real-time weather data source |
| Amazon S3 | Frontend hosting |
| CloudFront | Global CDN delivery |
| IAM | Permissions management |

## Cost

Near-zero monthly cost — Lambda runs only when requests come in.
OpenWeatherMap free tier supports 60 calls per minute.
