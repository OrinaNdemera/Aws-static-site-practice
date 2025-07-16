![Hosted on S3](https://img.shields.io/badge/Hosted%20on-AWS%20S3-orange?logo=amazon-aws&style=flat)
![Deployed via CloudFront](https://img.shields.io/badge/CDN-AWS%20CloudFront-brightgreen?logo=amazon-aws&style=flat)
![HTML Project](https://img.shields.io/badge/Language-HTML-blue?logo=html5&style=flat)
![AWS Certified](https://img.shields.io/badge/AWS%20Certified-Cloud%20Practitioner-yellow?logo=amazon-aws&style=flat)
![Status](https://img.shields.io/badge/Status-Completed-blueviolet)

# AWS Static Website Practice Project

This project is a simple, secure static website hosted on Amazon S3 and served via Amazon CloudFront. It showcases my ability to deploy and secure a web project using core AWS services.

## Live Demo

🔗 [View the site via CloudFront](https://dv64yihyaj60o.cloudfront.net)

##  What I Used

- **Amazon S3** – to host my static files (HTML + CV PDF)
- **Amazon CloudFront** – for secure HTTPS delivery and CDN caching
- **Bucket Policy** – to allow public read access
- **CloudFront Default Root Object** – to serve `index.html` at the root path

## Key Features

- Fully static website (HTML + download link)
- Responsive layout using inline CSS
- Secured via HTTPS using CloudFront
- Resume download option
- Clean, left-aligned layout

##  Challenges Faced

### 1.  Site Not Secure
- **Issue:** S3 website endpoint only supports HTTP, not HTTPS.
- **Fix:** Created a CloudFront distribution and configured it to serve content from the S3 bucket securely.

### 2.  Access Denied on CloudFront
- **Issue:** CloudFront returned a 403 Access Denied error.
- **Fix:** 
  - Changed the CloudFront origin to point to `s3.amazonaws.com` endpoint (not the `s3-website` one).
  - Ensured public access was allowed and bucket policy permitted `s3:GetObject`.
  - Set **Default Root Object** in CloudFront to `index.html`.

### 3.  Default Root Missing
- **Issue:** Visiting the root CloudFront URL gave "Access Denied".
- **Fix:** Set the **Default Root Object** to `index.html` under the General settings tab.

##  Lessons Learned

- HTTPS isn't available on S3 website URLs — CloudFront is needed
- Always set a default root object in CloudFront
- Public S3 buckets need the correct policy and open access settings
- CloudFront caching means you need to invalidate changes to see updates immediately

##  Files Included

- `index.html` – Main website structure

##  Future Improvements

- Use a custom domain (e.g., `orinacv.com`) for branding
- Add GitHub Actions to automate deployment to S3
- Style the site further using external CSS 
