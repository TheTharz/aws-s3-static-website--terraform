Got it! Here's the documentation with the GitHub repository URL added:

---

# Terraform AWS Portfolio Setup

This Terraform configuration sets up an AWS S3 bucket to host a portfolio website. It includes configurations for bucket creation, ownership controls, public access settings, website hosting, and object uploads.

## Terraform Files Overview

### `provider.tf`

This file specifies the AWS provider and its configuration options.

- **`aws` Provider Configuration:**
  - `region`: Specifies the AWS region as `eu-north-1`.

### `main.tf`

This file contains the main Terraform configurations for creating resources.

- **S3 Bucket Creation:**
  - Creates an S3 bucket named `var.bucketname`.
- **Bucket Ownership Controls:**
  - Configures ownership controls for the bucket to use "BucketOwnerPreferred".
- **Public Access Block:**
  - Configures public access settings for the bucket to allow public ACLs, policies, and buckets.
- **Bucket ACL:**
  - Sets the bucket ACL to "public-read".
- **Object Uploads:**
  - Uploads `index.html`, `error.html`, and `image.png` files to the bucket.
- **Website Hosting Configuration:**
  - Configures the bucket for static website hosting.
  - Sets `index.html` as the index document and `error.html` as the error document.

### `variable.tf`

This file defines Terraform variables used in the configuration.

- **`bucketname` Variable:**
  - Defines a variable for the S3 bucket name, with a default value of "myterraformportfoliobucket3996".

## Variable Configuration

To customize the deployment, modify the `variable.tf` file to set your desired bucket name.

## Deployment Steps

1. **Clone the Repository:**
   ```
   git clone https://github.com/TheTharz/aws-s3-static-website--terraform
   ```

2. **Navigate to the Directory:**
   ```
   cd aws-s3-static-website--terraform
   ```

3. **Initialize Terraform:**
   ```
   terraform init
   ```

4. **Review and Modify Variables:**
   Update the `variables.tf` file to set your desired bucket name.

5. **Deploy Infrastructure:**
   ```
   terraform apply
   ```
   Confirm the deployment by entering `yes`.

6. **Access the Website:**
   Once the deployment is complete, access your website at `http://<your_bucket_name>.s3-website.<region>.amazonaws.com`.

## Cleanup

To remove the deployed infrastructure, run:
```
terraform destroy
```
Enter `yes` to confirm destruction.

---

This documentation provides a detailed explanation of the Terraform configurations, deployment process, and cleanup steps for setting up an AWS S3 bucket to host a portfolio website. You can find the code in the [GitHub repository](https://github.com/TheTharz/aws-s3-static-website--terraform).
