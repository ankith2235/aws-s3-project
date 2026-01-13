# AWS S3 Implementation – XYZ Corporation

## 📌 Overview
XYZ Corporation requires a cloud-based storage solution capable of:
- Uploading and storing files
- Publicly sharing objects when needed
- Retaining past versions of files
- Hosting a static website
- Managing storage lifecycle automatically

This implementation uses **Amazon S3** to fulfill requirements.

---

## ✔️ Task 1 – Create S3 Bucket & Upload Files

### 🎯 Goal
1. Create an S3 bucket  
2. Upload 5 files with different file extensions  

### 🛠 Steps
- Logged into AWS Console → Opened **S3**
- Created a **new S3 bucket** with a unique bucket name
- Disabled “Block Public Access” if public sharing required
- Uploaded 5 files:
  - example.txt  
  - example.jpg  
  - example.png  
  - example.pdf  
  - example.docx

### 🧪 Outcome
✔ Bucket created successfully  
✔ All 5 files visible in S3 console  
✔ Public access works where enabled

---

## ✔️ Task 2 – Enable Versioning

### 🎯 Goal
1. Enable versioning on the same bucket  
2. Upload two files again to generate versions  

### 🛠 Steps
- Opened bucket → **Properties**
- Turned **Versioning** ON
- Re-uploaded:
  - example.txt
  - example.pdf
- S3 created additional versions instead of replacing files

### 🧪 Outcome
✔ Multiple versions visible under each object  
✔ Versioning protects files from accidental overwrite or delete

---

## ✔️ Task 3 – Static Website Hosting + Lifecycle Rule

### 🎯 Goal
1. Host a static website on S3  
2. Add storage lifecycle rules:
   - Standard → Standard-IA after 60 days  
   - Delete/Expire after 200 days  

### 🛠 Steps

#### 🌐 Static Website Hosting
- Properties → Enabled **Static Website Hosting**
- Set:
  - `index.html`
  - `error.html`
- Uploaded both HTML files
- Tested website using S3 **Website Endpoint URL**

#### 🔁 Lifecycle Rule
- Opened **Management → Lifecycle rules**
- Created rule to:
  - Transition Standard → Standard-IA in 60 days
  - Expire objects at 200 days
- Applied to all objects in bucket

### 🧪 Outcome
✔ Static website loads from S3  
✔ Error page shows for invalid paths  
✔ Lifecycle policy applied successfully  
✔ Storage automatically optimized over time

---

## 🧰 Tools Used
- AWS Management Console  
- Amazon S3

---

## 🎉 Final Result
The bucket now supports:
- Secure and scalable object storage
- Public file sharing capability
- Versioning and data protection
- Static website hosting
- Cost-saving lifecycle automation

---

## 🚀 Future Enhancements (Optional)
- Add IAM policies for user access control
- Deploy CloudFront CDN for faster delivery
- Enable logging and encryption (KMS)
- Automate uploads with AWS CLI or SDK
