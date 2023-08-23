# Mlflow deployment on k8s using ansible

Deploying MLflow on Kubernetes (K8s) using Ansible involves automating the process of creating the necessary Kubernetes resources and configurations for running MLflow services. Here's a brief overview of the steps involved:

Setting up Ansible:
Make sure you have Ansible installed on your local machine or the server you're using for deployment.

Creating Ansible Playbooks:
Create Ansible playbooks to define the deployment process. Ansible playbooks are YAML files that contain a series of tasks to be executed.

Creating Kubernetes Configurations:
In your Ansible playbooks, you'll need to create Kubernetes resources such as deployments, services, and possibly ingress rules. You can use Ansible's k8s module to manage these resources.

Configuring MLflow:
Your playbook should also include steps to configure MLflow. This may involve creating a configuration file for MLflow with the necessary settings, including database connections and storage configurations.

Applying Playbooks:
Run the Ansible playbooks using the ansible-playbook command. Ansible will execute the tasks defined in the playbook and create the specified Kubernetes resources.

Verifying Deployment:
After the deployment is complete, you can verify that MLflow services are up and running within your Kubernetes cluster. Check the status of pods, services, and any other relevant resources.

### Run Ansible Playbook:

Open a terminal and navigate to the directory containing your Ansible playbook and Kubernetes configuration files. Run the following command:

```
ansible-playbook -i inventory.yml k8s_mlflow.yml
```

### if docker fails to build run below commands in all nodes:

```
systemctl restart NetworkManager.service
```

```
sudo service docker restart
```
