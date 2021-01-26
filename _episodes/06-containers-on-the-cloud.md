---
title: "Creating containers in the cloud"
teaching: 20
exercises: 0
questions:
- "How can I create Docker containers in the cloud?"
objectives:
- "Demonstrate how to effect creation of a container from the Docker image in the cloud."
- "Gain an initial experience of the container functionality provided by the Bitbucket repository storage service."
keypoints:
- "You can create Docker containers on cloud computing resources just using a web browser."
- "Bitbucket is an online repository storage service that can create Docker containers to perform computation in response to files changing in your repositories."
---
## Creating Containers on Cloud Platforms
There are lots of ways containers can be created on cloud computing platforms (a.k.a., "in the cloud"). Most commercial cloud providers now offer a container hosting service that will connect to the Docker Hub (and their own container registries) in order to fetch the container images that you specify, and charge for the time and resources that the containers use.

## Free and Introductory Offer Container Hosting Options 

Please note these options can be constantly changing, check with the Cloud providers webpage for the latest details. Beware that many of the free trials require you to give payment information and you will be billed at the end of the trial or if you exceed the free trial limits. Many of the cloud providers offer charge limit options, set these to ensure you don't get an sudden large bill. 

## Educational Credits
For this lesson (run by AIMLAC CDT, January 2021) we have received free credit from Google for $50 per student, you will not need to register a credit card to use this. You will have each been emailed a link to activate this.

{% comment %}

#### Google Cloud

$300 free credit for 3 months when you signup and give credit card details. Free f1-micro VM with 1 shared CPU, 600 MB of RAM and 10GB disk. Free 50 hours per month of Cloud Run time which launches containers to handle web requests. 
https://cloud.google.com/free

#### Microsoft Azure
$100 free credit for students signing up via the Github student pack. 
https://education.github.com/pack?sort=popularity&tag=Cloud

$200 free trial for 30 days. 12 months free B1S virtual machine.
https://azure.microsoft.com/en-gb/offers/ms-azr-0044p/

#### Amazon Web Services
750 hours per month free t2.micro or t3.micro virtual machine for the first 12 months.
https://aws.amazon.com/free/

#### Digital Ocean 
$100 free credit for students signing up via the Github student pack.
https://education.github.com/pack?sort=popularity&tag=Cloud

{% endcomment %}

### Running a container in the cloud, using your Google account

- Open a web browser window and visit <https://console.cloud.google.com/>.
- Log into your Google account.
- Click billing
- Click on the grill menu, Compute Engine, VM Instances

![VM instances](screenshots/gcloud_step1.png)

- Click on "Create Instance" on the page showing the list of current instances.
- Give your VM a name, as we won't need much processing power choose f1-micro as the Machine type by selecting the N1 Series.
- Change the operating system to the Container Optimised OS

![Cloud OS](screenshots/gcloud_step2.png)

#### SSH into your container from the Google Cloud Console

- If for whatever reason you need to login to the instane then click on the SSH option under the connect column in the VM Instances page and choose "Open in browser Window."

![SSH to VM](screenshots/gcloud_step6.png)
![SSH to VM](screenshots/gcloud_step7.png)

- From here you can run docker commands and see the container we specified is running.

![SSH to VM](screenshots/gcloud_step8.png)

When using the `docker run` command (as you have done previously), the container takes some default actions after being created, which are specified in your Dockerfile (e.g., the `CMD` line).

#### SSH into your container from your computer's SSH client

#### Destroying your virtual machine 

### Running a web server container from Google Clound

Go back to the Cloud console. 

- Click on "Create Instance" on the page showing the list of current instances.
- Give your VM a name, as we won't need much processing power choose f1-micro as the Machine type by selecting the N1 Series.
- Tick the option "Deploy a container image to this VM instance".
- Enter the path to your container on Docker Hub (in this case colinsauze/5min-cloud-docker) in the "Container image" box.
- Scrolldown and tick "Allow HTTP traffic" at the bottom of the page under Firewall

![Allow HTTP](screenshots/gcloud_step3.png)

- Click create

- Go back to the VM Instances page in the Google Cloud Console and click on the link to the external IP address (104.154.185.63 in this example) or type this address into a new tab/window of your web browser.

![List of instances](screenshots/gcloud_step4.png)

- You should see a webpage giving the time and a random number.

![Working webpage](screenshots/gcloud_step5.png)

- Don't forget to delete the instance when you are done with it.

{% include links.md %}

{% comment %}
<!--  LocalWords:  keypoints links.md endcomment Dockerfile
 -->
{% endcomment %}
<!--  LocalWords:  bitbucket-pipelines.yml
 -->
