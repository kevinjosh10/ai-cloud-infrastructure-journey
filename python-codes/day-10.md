# Day 052 – Python Practice Code

**Date:** 22 April 2026  
**Day in Python Journey:** Day 52  

---

## 🎯 Objective

Practice using boto3 (AWS SDK for Python) to interact with Amazon S3 by creating buckets, listing them, and performing file upload/download operations.

---

## 🧾 setup_boto3.py

    import boto3

    # Create S3 client
    s3 = boto3.client('s3')

    print("boto3 setup successful!")

---

## 🧾 list_buckets.py

    import boto3

    s3 = boto3.client('s3')

    response = s3.list_buckets()

    print("Your S3 Buckets:")

    for bucket in response['Buckets']:
        print("-", bucket['Name'])

---

## 🧾 create_bucket.py

    import boto3

    s3 = boto3.client('s3')

    bucket_name = "my-test-bucket-kevin-12345"  # Must be globally unique

    s3.create_bucket(
        Bucket=bucket_name,
        CreateBucketConfiguration={
            'LocationConstraint': 'ap-south-1'
        }
    )

    print("Bucket created:", bucket_name)

---

## 🧾 upload_file.py

    import boto3

    s3 = boto3.client('s3')

    bucket_name = "my-test-bucket-kevin-12345"

    # Upload file
    s3.upload_file('local.txt', bucket_name, 'remote.txt')

    print("File uploaded to S3")

---

## 🧾 download_file.py

    import boto3

    s3 = boto3.client('s3')

    bucket_name = "my-test-bucket-kevin-12345"

    # Download file
    s3.download_file(bucket_name, 'remote.txt', 'downloaded.txt')

    print("File downloaded from S3")

---

## 🧠 Concepts Practiced

- boto3 basics  
- AWS S3 operations  
- Clients vs resources  
- File upload and download  
- Working with cloud storage  

---

## ▶️ Commands Used

    python3 setup_boto3.py
    python3 list_buckets.py
    python3 create_bucket.py
    python3 upload_file.py
    python3 download_file.py

---

## 💭 Reflection

Learned how to interact with AWS using Python.  
Understood how cloud storage works through S3.  
Took first step into real cloud automation using code.

---

**Status:** Day 52 of Python Complete ✅  