---
icon: aws
---

# AWS S3

#### AWS S3

This is a guide for connecting **Weekerp CDN** with **Amazon S3**.

It explains how to create an IAM account and register it with Weekerp.

***

#### Required Information

To allow Weekerp to access your images, you’ll need to provide the following details:

* **Access Key ID**
* **Secret Access Key**
* **Bucket Name**

***

#### Getting Credentials

If you’re not familiar with AWS, we recommend **creating a dedicated IAM user** that grants Weekerp read-only access to your S3 bucket.

1. Open the **Amazon IAM (Identity and Access Management)** console.
2. Go to **Users → Create user**.
3. Make sure to enable **“Programmatic access”**.
4. Under the **Permissions** tab, choose **“Attach existing policies directly.”**
5. Search for and select **“AmazonS3ReadOnlyAccess.”**
6. Complete the process to receive your **Access Key** and **Secret Key**.

***

#### Connecting to Weekerp

After logging into Weekerp, navigate to:\
**Sources → Add Source → Amazon S3**

Enter the credentials you obtained above.

***

#### Visual Setup Guide

**1.** Open the **AWS Management Console**, and search for **IAM**.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



**2.** In the left navigation bar, click **Users**, then click **Create user** at the top right.

**3.** Enter the user name, for example `weekerp-cdn-reader`, and click **Next**.

**4.** Under **Permissions**, search for **AmazonS3ReadOnlyAccess**, select it, and click **Next**.

If you prefer to attach a custom policy manually, the required permissions are as follows:

```json
{
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:ListBucket",
        "s3:GetBucketLocation"
      ],
      "Resource": [
        "arn:aws:s3:::my-bucket/*",
        "arn:aws:s3:::my-bucket"
      ]
    }
  ]
}
```

**5.** Review the creation result and click **View User**.

**6.** Open the **Security Credentials** tab.

**7.** Scroll down and click **Create access key**.

**8.** Add a description (optional) and click **Create access key** again.

**9.** Check the result and (recommended) **download the CSV file** containing your keys.

***

#### Registering with Weekerp

**10.** Go to **Weekerp → Sources → Add Source → Amazon S3**.

**11.** Enter the credentials you generated earlier.

**BasePath** defines the root directory within your bucket.

Example:

```
/dog.jpg  
/assets/cat.png
```

In this case, BasePath can be `/` (root) or `/assets`.

**12.** Assign a unique identifier.\
This identifier will be used in your CDN URL:

```
https://cdn.weekerp.com/image/{unique-identifier}/dog.jpg?s=200x200
```

**13.** Verify the created CDN connection.\
Once setup is complete, it typically takes **5–10 minutes** for propagation across all global edge locations.
