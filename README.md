# Urlzinha - Microservices for URL Shortening

**Urlzinha** is a microservices-based application that provides URL shortening and redirection capabilities. This project was developed during a course by [RocketSeat](https://www.rocketseat.com.br). The system is split into two independent projects: **URL Generation** and **URL Redirection**, both implemented as AWS Lambda functions integrated with S3 for data storage and API Gateway for routing.

---

## **Project: URL Generation**

### **Description**
This microservice generates a shortened URL for a given original URL with a specified expiration time. The generated data is stored in an S3 bucket for future retrieval.

### **Key Features**
- **API Gateway**: Exposes the Lambda function via an HTTP POST endpoint.
- Accepts a JSON input containing:
    - `originalUrl`: the original URL to shorten.
    - `expirationTime`: expiration time in seconds.
- Generates a unique 8-character code.
- Stores URL data in an S3 bucket in JSON format.

### **Input Example**
```json
{
  "originalUrl": "https://example.com",
  "expirationTime": "3600"
}
```

### **Output Example**
```json
{
  "code": "abcd1234"
}
```

### **API Gateway Configuration**
- **HTTP Method**: POST
- **Endpoint**: `/generate`
- **Request Payload**: JSON body containing the URL data.


_Access the project to redirect here: [URL Redirection](https://github.com/Vogon38/urlzinha-redirect-url-rocketseat)_




