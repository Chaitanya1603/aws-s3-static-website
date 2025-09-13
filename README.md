# AWS S3 Static Website Deployment

A comprehensive project demonstrating how to deploy a static website to AWS using S3, CloudFront, and IAM policies.

## 📋 Project Overview

This project showcases the deployment of a static website to Amazon Web Services (AWS) using best practices for hosting, security, and content delivery. The website includes only client-side technologies (HTML, CSS, and JavaScript) and requires no server-side processing, making it perfect for AWS S3 static website hosting.

## 🏗️ Architecture

The project implements the following AWS architecture:

- **Amazon S3**: Static website hosting and file storage
- **AWS CloudFront**: Content Delivery Network (CDN) for improved performance
- **AWS IAM**: Identity and Access Management for security policies

## ✅ Prerequisites

Before starting this project, ensure you have:

- An active AWS account
- AWS CLI installed and configured
- Basic knowledge of HTML, CSS, and JavaScript
- Understanding of AWS S3, CloudFront, and IAM concepts

## 🚀 Deployment Steps

### Step 1: Create and Configure S3 Bucket

1. **Create S3 Bucket**
   - Navigate to S3 in AWS Console
   - Create a new bucket with a unique name
   - Choose appropriate region
   - Keep default settings for now

2. **Configure Static Website Hosting**
   - Go to bucket properties
   - Enable static website hosting
   - Set index document (e.g., `index.html`)
   - Set error document (e.g., `index.html`)

3. **Set Bucket Policy**
   - Configure public read access
   - Apply appropriate IAM policies for security

### Step 2: Upload Website Files

1. Upload your static website files:
   - HTML files
   - CSS stylesheets
   - JavaScript files
   - Images and other assets

2. Ensure proper file organization and naming conventions

### Step 3: Configure CloudFront Distribution

1. **Create CloudFront Distribution**
   - Set S3 bucket as origin
   - Configure caching behaviors
   - Set up custom error pages
   - Enable compression

2. **Configure Security Headers**
   - Set appropriate cache control headers
   - Configure HTTPS redirect if needed

### Step 4: Test and Verify

1. **Access via S3 Endpoint**
   - Test direct S3 website URL
   - Verify all pages load correctly
   - Check responsive design

2. **Access via CloudFront**
   - Test CloudFront distribution URL
   - Verify improved loading times
   - Check global accessibility

## 📁 Project Structure

```
aws-s3-static-website/
├── src/
│   ├── index.html          # Main landing page
│   ├── error.html          # Custom error page
│   ├── css/
│   │   └── style.css       # Stylesheet
│   ├── js/
│   │   └── script.js       # JavaScript functionality
│   └── assets/
│       └── images/         # Image files
├── screenshots/            # Project documentation
│   ├── s3-bucket-setup.png
│   ├── cloudfront-config.png
│   └── final-website.png
├── policies/
│   └── bucket-policy.json  # S3 bucket policy
└── README.md              # This file
```

## 🔧 Configuration Files

### S3 Bucket Policy Example

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::your-bucket-name/*"
        }
    ]
}
```

### CloudFront Configuration

- **Origin Domain**: Your S3 bucket website endpoint
- **Viewer Protocol Policy**: Redirect HTTP to HTTPS
- **Allowed HTTP Methods**: GET, HEAD
- **Cache Policy**: Managed-CachingOptimized

## 📸 Documentation Requirements

As per project specifications, include screenshots of:

1. S3 bucket creation and configuration
2. Static website hosting settings
3. IAM policy application
4. File upload confirmation
5. CloudFront distribution setup
6. Final website accessibility test
7. Performance metrics (optional)

## 🌐 Website URLs

- **S3 Static Website Endpoint**: `[http://[bucket-name].s3-website-[region].amazonaws.com](http://static-website-1603a.s3-website-us-east-1.amazonaws.com)`
- **CloudFront Distribution URL**: `[d1bcbn41ded6ts.cloudfront.net](https://d1bcbn41ded6ts.cloudfront.net/)`


## 🌐 Website URLs
- **S3 Static Website Endpoint**: [http://static-website-1603a.s3-website-us-east-1.amazonaws.com](http://static-website-1603a.s3-website-us-east-1.amazonaws.com)
- **CloudFront Distribution URL**: [https://d1bcbn41ded6ts.cloudfront.net/](https://d1bcbn41ded6ts.cloudfront.net/)


## 🧹 Cleanup Instructions

**⚠️ Important**: Delete all AWS resources after project completion to avoid charges:

1. Delete CloudFront distribution (allow time for deletion)
2. Empty and delete S3 bucket
3. Remove any associated IAM policies
4. Check for any remaining resources in your account

## 📊 Performance Benefits

Using CloudFront provides:
- **Global Edge Locations**: Reduced latency worldwide
- **Caching**: Improved load times for repeat visitors  
- **Bandwidth Optimization**: Reduced origin server load
- **DDoS Protection**: Built-in security features

## 🛠️ Troubleshooting

### Common Issues:

1. **403 Forbidden Error**
   - Check bucket policy permissions
   - Verify index document name
   - Ensure files are publicly readable

2. **CloudFront Not Serving Updated Content**
   - Create invalidation for updated files
   - Wait for distribution deployment
   - Check cache headers

3. **Website Not Loading**
   - Verify static website hosting is enabled
   - Check index document configuration
   - Confirm bucket name and region

## 📚 Learning Resources

- [AWS S3 Static Website Hosting Guide](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)
- [CloudFront Documentation](https://docs.aws.amazon.com/cloudfront/)
- [AWS IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

## 🤝 Contributing

Feel free to contribute to this project by:
- Improving documentation
- Adding new features
- Optimizing performance
- Sharing best practices

