

SURGE URL:

                                      http://spartafitness.surge.sh/




# Step#1

                                              git clone <repo>

# step#2

                                         gcloud builds submit --tag gcr.io/<PROJECT_ID>/<image-name> .

# step#3

Set up IAM:
-----------


Now on a coding perspective, you are all done. Now we need to configure a couple more resources to get this pipeline working in GCP. First is setting up IAM for cloud builder so that it has permissions to deploy the images in GKE.
To do this, navigate to IAM & Admin →IAM on the side menu.
Here, you would see an entry in the format,

                           <project-number>@cloudbuild.gserviceaccount.com

with the role, Cloud Build Service Account. Edit the role and add "Kubernetes Engine Admin" role to it as well.

# step#4

Create a new service account named "circleci-access" under "IAM & Admin"

Give some access Roles to this newly created service account. For example's sake we will use a bit relaxed permissions:

                           Storage/Storage Admin
               
                           Kubernetes Engine/Kubernetes Engine Developer

After setting permissions, create a key for this service account, by using "Create Key" button on next screen. Use type JSON. The key will download immediately to your computer, only once. Make a note of it's location. Keep it safe.


# step#5

Open circleCI dashboard

We setup GCLOUD_CREDENTIALS as environment variable . In the Project settings of this project, go to Environment variables, and add an environment variable called GCLOUD_CREDENTIALS. Copy the text of the JSON file from the text terminal and paste it in as a value for this variable.

----------------------------------------------------------------------------------------------------------------------------------------------------------------


tutorials:

https://github.com/ghazalrana/docker-to-kubernetes/blob/master/Migration-Part-3.md

https://www.youtube.com/watch?v=xxDRg9DLME8&list=PLxv9HL8TPbSxBEjcHPwTjvYBfioVmtT1W&index=3


