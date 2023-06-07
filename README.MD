# Deployment Process on AWS S3

This README file provides step-by-step instructions on deploying a React app on an AWS S3 bucket.

## Source Code & Demo Link:

- Live web-app link: http://gunjan-demo-s3.s3-website.ap-south-1.amazonaws.com
- Source code of above deployed web-app: https://github.com/gunjan2012/react-practical-7

## Prerequisites

- `AWS account` with appropriate permissions to create and manage S3 buckets.

## Deployment Process

### 1. Create an S3 bucket:

- Log in to your AWS Management Console.
- Navigate to the S3 service.
- Click on "Create bucket" to create a new bucket.
- Here i had created the `gunjan-demo-s3` as bucket name.

![bucket](/assets/create_bucket.png)

### 2. Configure the S3 bucket for static website hosting:

- Open the bucket you just created in the S3 console.
- Go to the "Properties" tab and scroll down to the "Static website hosting" section.
- Select "Use this bucket to host a website".
- Enter the name of your index.html file as the "Index document".

![static](/assets/static.png)

### 3. Build your React application:

- Run npm run build to build the optimized production-ready version of your React app.
- After the build process completes, a build folder will be generated with the bundled files.

### 4. Upload the build files to your S3 bucket:

- In the S3 console, go to the "Overview" tab of your bucket.
- Click on the "Upload" button.
- Select the files and folders inside the build folder.

![public](/assets/build-objects.png)

### 5. Enable public access permission of our bucket:

- Go to permission tab and edit the Block public access and in that uncheck the `Block public access`.
- After this public access is granted to buckets.

![public](/assets/permissions.png)

### 6. Configure bucket policies for static website hosting:

- Go to permission tab and add following policy which allows public read access to the objects in your bucket:
- Here you can change the bucket name from Resource property with your bucket name.
- Click "Save" to save the policy.

![public](/assets/bucket-policy.png)

### 7. Access your deployed React app:

- In the S3 console, go to the "Properties" tab of your bucket.
- Locate the "Static website hosting" section and copy the "Endpoint" URL.
- Open a web browser and paste the copied URL.
- Your React app should now be accessible and deployed on AWS S3.

![public](/assets/static-website.png)
