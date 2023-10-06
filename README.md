
# Continuous Deployment for Static Website to AWS S3 with GitHub Actions

This guide will walk you through setting up continuous deployment (CD) for a static website hosted in an AWS S3 bucket using GitHub Actions. This setup allows you to automatically deploy changes to your website whenever there's a push to the `main` branch of your GitHub repository.

## Prerequisites

Before you begin, make sure you have the following prerequisites in place:

1. An AWS account with an S3 bucket set up to host your static website.

2. An AWS CloudFront distribution set up for your S3 bucket.

3. A GitHub repository containing your static website's source code.

4. Create new user in AWS for your GitHub (don't forget to save AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY). 

5. Give permissions for new user with IAM sample policies 'Create_Invalidation_CloudFront' and 'AmazonS3FullAccess' files of this repo.



## GitHub Actions Configuration

To set up CD for your static website, follow these steps:

### 1. Create a GitHub Actions Workflow

In your GitHub repository, create a `.github/workflows/main.yml` file with the content from main.yml file in this repo.

### 2. Add GitHub Secrets
In your GitHub repository settings, go to "Settings" -> "Secrets" and add the following secrets:

AWS_ACCESS_KEY_ID: Your AWS IAM access key ID.
AWS_SECRET_ACCESS_KEY: Your AWS IAM secret access key.
CLOUDFRONT_DISTRIBUTION_ID: Your CloudFront distribution ID.

### 3. Commit and Push
Commit the .github/workflows/main.yml file to your repository and push it to the main branch. This will trigger the GitHub Actions workflow whenever changes are pushed to main.


### Conclusion
With this setup, your static website will be automatically deployed to your S3 bucket and the CloudFront cache will be invalidated whenever changes are pushed to the main branch of your GitHub repository.

Now, you have a fully automated CD pipeline for your static website on AWS S3 using GitHub Actions!

