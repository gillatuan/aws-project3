I. Create an EKS Cluster
    - Create IAM role
      - Check IAM Permission
    - Create an EKS Cluster
    - Update the Kubeconfig
    - Verify and copy the context name
    - Delete the EKS Cluster (if not used)

II. Configure a Database for the Service
  Before you start, ensure you are connected to your K8s cluster 
  1. Create YAML Configurations
      kubectl get namespace
      1.1 Create PersistentVolumeClaim
      1.2 Create PersistentVolume
      1.3 Create Postgres Deployment 2. Apply YAML configurations 3. Test Database Connection 4. Connecting via Port Forwarding 5. Run Seed Files 6. Checking the tables 7. Closing the forwarded ports

III.Build the Analytics Application Locally
  Once you have set up the database, you may proceed to build the analytics application.
  First, let's try running the application locally, without Docker.
  In the analytics/ directory: 1. Install Dependencies 2. Run the Application 3. Verify the Application

IV.Deploy the Analytics Application
  Once you have verified that the application code runs successfully, you may now begin the deployment process. The deployment process is divided into three steps:
  Dockerize the application
  Set up Continuous Integration with CodeBuild
  Deploy the application on Kubernetes
  You may follow the step-by-step instructions on this page to help you complete this part of the project. 
  1. Dockerize the Application
    1.1. Update Docker Version
    1.2. Build and Run a Docker Image
    1.3. Verify the Docker Image 
  2. Set up Continuous Integration with CodeBuild
    2.1. Setting Up
    2.2. Verify  
  3. Deploy the Application
    3.1. ConfigMap
    3.2. Secret
    3.3. Deployment 4. Verify the Deployment
    
V. Setup CloudWatch Logging
  Container Insights can be installed to your CloudWatch to give you periodic application logging that will be useful to periodically check your application's health.
  To do this, you may follow the following tutorial from AWS to install Amazon CloudWatch Observability EKS add-on:
  Install the CloudWatch agent by using the Amazon CloudWatch Observability EKS add-on(opens in a new tab)
  All you need to do is run a couple of short commands on your terminal:
  Step 1. Attach the CloudWatchAgentServerPolicy IAM policy to your worker nodes:
  Step 2. Use AWS CLI to install the Amazon CloudWatch Observability EKS add-on:
  Step 3. Trigger logging by accessing your application.
  Step 4. Open up CloudWatch Log groups page. You should see aws/containerinsights/my-cluster-name/application there.
