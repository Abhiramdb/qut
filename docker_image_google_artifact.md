# Setting up in All of Us -- Research Wrokbench
# Using Docker Images on Google Cloud Artifact Registry

This guide explains how to pull a Docker image from Docker Hub, push it to Google Cloud Artifact Registry, and make it publicly available for analysis.

## Set Up Google Cloud Project

1. Open a Gmail account (other than @researchallofus.org) linked to a credit card for Google Cloud.
2. Create a new project or use an existing one.
3. (Optional) Make the project publicly accessible — check Google Cloud project settings if needed.
4. Note the Project ID (e.g., projectID). This will be used in the Artifact Registry.

---

# 2. Access Artifact Registry

1. In the [Google Cloud Console](https://console.cloud.google.com), search for **Artifact Registry**.  
2. Open the Artifact Registry page.  
3. Open the **Cloud Shell terminal** (top-right corner).  

> Using the Cloud Shell exempts you from running `gcloud auth login` and `gcloud auth configure-docker`.

---
# 3. Pull, Tag, and Push Docker Image

```bash
# Pull the Docker image from Docker Hub
docker pull zijingliu/ldsc

# Tag the Docker image for your Google Cloud project
docker tag zijingliu/ldsc gcr.io/<projectID>/ldsc:latest

# Push the Docker image to Artifact Registry
docker push gcr.io/<projectID>/ldsc:latest
```

-  Docker Hub link: https://hub.docker.com/r/zijingliu/ldsc
-  Research AllOfUs support: Using Docker Images on the Workbench

# 4. Make the Image Public

1. Go to the Artifact Registry folder for your project: E.g.: https://console.cloud.google.com/artifacts?project=<projectID>
2. Select the folder containing your image (`gcr.io`).
3. Open the Info Panel (right corner).
4. Go to Permissions → Add Principal.
5. Add a new principal:
   -  Type: allUsers
   -  Role: Basic → Viewer
6. Save the changes. The Docker image is now publicly accessible.

# 5. Use Docker Image in Analysis

Once the image is pushed and public, you can reference it in your analysis:
```bash
# Example: specify Docker image for analysis
--image gcr.io/<projectID>/ldsc:latest
```
