Static Website — Hosted on AWS Amplify 

A static website built with HTML and CSS, continuously deployed via AWS Amplify connected to a GitHub repository.

What is AWS Amplify?

AWS Amplify is a fully managed hosting platform by Amazon Web Services. It takes your code directly from a Git repository, builds and deploys it automatically,
and serves it globally through a CDN (Content Delivery Network). Every time you push a change to GitHub, Amplify picks it up and redeploys(no manual steps required).

For a static website, Amplify acts as:
* A build pipeline — detects code and prepares it for deployment
* A CDN host — serves website files from edge locations around the world for fast load times
* An SSL provider — gives website an HTTPS automatically
* A CI/CD system — redeploys on every Git push

Hosting Procedure:

Prerequisites:
* AWS Account
* project code pushed to a GitHub repository

Step 1: Commit project code to Github repo
Step 2: Connect Github to AWS Amplify
1. Sign in to the AWS Amplify Console.
2. Click "Create new app".
3. Under Host your web app, select GitHub and click Next.
4. Authorize AWS Amplify to access GitHub account when prompted.
5. Select your repository and the branch you want to deploy (e.g. main).
6. Click Next.

Step 3: Configure Build Settings
For a plain HTML/CSS site, no build command is needed, Amplify auto-detects this.
* Build command: leave empty
* Output directory: / (root of the project)
Review the settings and click Save and Deploy.

Step 4: Wait for deployment
* AWS Amplify will go through 4 stages, Provision, Build, Deploy, and Verify. Once all stages are green, live URL will be generated for the website.
  
My live URL: https://main.d12zdgqjghz6w7.amplifyapp.com

Step 5: Setup the custom 404 pages
By default, Amplify doesn't know which page to show for missing URLs, 
so we need to manually add a redirect rule in Hosting → Rewrites and Redirects section.
Now any unknown URL will serve your custom error.html page

Step 6: Set up custom domain(optional)
In Amplify Console, go to Hosting → Domain Management, click Add domain, and enter your custom domain name.
Amplify will give you DNS records to add in your domain registrar.Once propagated, site goes live on your custom domain with a free SSL certificate.

Environment Overview:

Hosting -	AWS Amplify

Source Control - GitHub

Branch - main

Build Type - Static (no build command)

HTTPS -	Enabled automatically

CDN	- AWS CloudFront (global)

Auto-deploy	- Yes(on every push to main)


Useful links

https://docs.aws.amazon.com/AmazonS3/latest/userguide/website-hosting-amplify.html
https://docs.aws.amazon.com/hands-on/latest/host-static-website/host-static-website.html


