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

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>



**2.** In the left navigation bar, click **Users**, then click **Create user** at the bottom right.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>



**3.** Enter the user name, for example `weekerp-cdn-reader`, and click **Next**.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>



**4.** Under **Permissions**, search for **AmazonS3ReadOnlyAccess**, select it, and click **Next**.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

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

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>



**6.** Open the **Security Credentials** tab.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>



**7.** Scroll down and click **Create access key**.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



**8.** Add a description (optional) and click **Create access key** again.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>



**9.** Check the result and (recommended) **download the CSV file** containing your keys.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>



***

#### Registering with Weekerp

**10.** Go to  [**Weekerp**](https://weekerp.com/space/callback) **→ Sources → Add Source → Amazon S3**.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>



**11.** Enter the credentials you generated earlier.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**BasePath** defines the root directory within your bucket.
{% endhint %}

Example:

```
/dog.jpg  
/assets/cat.png
```

In this case, BasePath can be `/` (root) or `/assets`.

For more details, please refer to [basepath.md](../basepath.md "mention")



**12.** Assign a unique identifier.

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

\
This identifier will be used in your CDN URL:

```
https://cdn.weekerp.com/image/{unique-identifier}/dog.jpg?s=200x200
```



**13.** Verify the created CDN connection.\
Once setup is complete, it typically takes **5–10 minutes** for propagation across all global edge locations.
