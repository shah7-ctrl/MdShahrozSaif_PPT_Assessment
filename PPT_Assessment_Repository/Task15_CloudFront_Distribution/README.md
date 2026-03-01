

#### To host a static website on Amazon S3 and improve its global performance using Amazon CloudFront (CDN).



This task demonstrates understanding of:



\* Static website hosting

\* Content Delivery Networks (CDN)

\* Global content distribution

\* Performance optimization



---



\## 🛠️ Services Used



\* Amazon S3

\* Amazon CloudFront

\* Amazon Web Services



---



\## 🏗️ Architecture Overview



1\. Static website files (HTML, CSS, JS) are stored in an S3 bucket.

2\. S3 static website hosting is enabled.

3\. CloudFront distribution is created.

4\. CloudFront fetches content from S3 and caches it globally.

5\. Users access the website through CloudFront URL for faster delivery.



---



\## ⚙️ Step-by-Step Implementation



\### Step 1: Create S3 Bucket



1\. Go to \*\*S3 Dashboard\*\*

2\. Click \*\*Create Bucket\*\*

3\. Enter a unique bucket name

4\. Disable “Block all public access” (for static hosting)

5\. Create bucket



---



\### Step 2: Upload Website Files



Upload:



\* `index.html`

\* `style.css` (optional)

\* Any images or JS files



---



\### Step 3: Enable Static Website Hosting



1\. Go to \*\*Bucket → Properties\*\*

2\. Enable \*\*Static Website Hosting\*\*

3\. Set:



&nbsp;  \* Index document: `index.html`

4\. Save changes



Copy the S3 Website Endpoint URL.



---



---



\### Step 4: Create CloudFront Distribution



1\. Go to \*\*CloudFront\*\*

2\. Click \*\*Create Distribution\*\*

3\. Origin Domain:



&nbsp;  \* Select your S3 bucket

4\. Viewer Protocol Policy:



&nbsp;  \* Redirect HTTP to HTTPS (Recommended)

5\. Default Root Object:



&nbsp;  \* `index.html`

6\. Click \*\*Create Distribution\*\*



Wait for status to change from \*\*Deploying → Deployed\*\*





---



\## 📊 Expected Output



| Component         | Result                     |

| ----------------- | -------------------------- |

| S3 Static Hosting | Website accessible         |

| CloudFront        | Distribution created       |

| CDN URL           | Website loads successfully |

| Performance       | Faster global access       |





---



\## 🧠 Real-World Use Case



This setup is commonly used for:



\* Portfolio websites

\* Company landing pages

\* Documentation sites

\* Frontend applications (React, Angular, Vue)



Major companies use CDN-based architecture to serve global traffic efficiently.



---



\## 📌 Conclusion



In this project, we successfully hosted a static website on S3 and distributed it globally using CloudFront. CloudFront acts as a CDN, improving performance, security, and scalability.



This task demonstrates practical knowledge of global content delivery using AWS services.



---





