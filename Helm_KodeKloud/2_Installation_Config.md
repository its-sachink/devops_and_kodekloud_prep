## Installation and configuration

</br>
</br>
</br>
</br>

#### 1: What is Helm :
</br>
- Managing the YAML file is tedious, editing each different YAML file would be challenging.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f2fed4ea-6909-4f16-9904-436388750fe8)

</br>
- HELM is also called a package manager for Kubernetes.
- We tell what package HELM needs to act on like, installing the Wordpress application.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2ba78fc0-f301-4957-9fa8-f8a8a9bf29fb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/16809979-8ca4-4f05-ab82-5d482ca45361)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ebf14227-fef6-4bbe-aa7d-50b51f867bc1)


#### 2: Helm2 vs Helm3 :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b0fe216b-2bce-491c-8dad-ef93db08cede)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/756a1a6f-f4f0-44f2-968a-9b8cf6baf9e0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/30f4035c-bb93-4d39-8350-187efb23d637)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f5bdda0d-7b42-412b-a7c9-e5b48bbccaf0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3907c5e0-41d0-44f5-9d41-0d68723d7c9a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9c007d0c-e368-4b4b-b962-4ac96a72f85f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ee3d70bc-ba3e-4598-8353-acab21632499)

- HELM is more intelligent, it compares the current chart in use with for which we didn't created a revision (as we performed the manual upgrade) here with the Revision:1.
- It also checks for the lives states of the kubernetes objects as to how it look like. There declaration in the YAML form.
- This is called "3-Way Strategic Merge Patch".
- It always look at the live state with the image version we want to rollback to.
- HELM3 looks at the old chart and new chart, and it preserves the stuff that you might have manually added.

</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/339b278f-7bfb-4302-bcee-5454c10f73d5)


- HELM Components :
  - HELM CLI
  - Charts are a collection of files to create the collections of objects to be created on the K8s cluster.
  - When a chart is applied to your cluster a release it created. A release is a single installation of an application within a HELM chart.
  - A Release can have multiple revisions, and each revision is like a SNAPSHOT of an application.
      - Everytime a changes made to application such as upgrade of image, change of replicas or configuration objects a new revision is created.
  - We can find HELM charts in a public repository.
      - We can use it to deploy applications on our cluster.
  - To keep track of what it did in our cluster, like releases it installed, the chart it used, the revision state and so on.
      - HELM needs a place to save this data, this data is called as a metadata.
      - HELM stores this data in our kuberenetes cluster a kubernetes secrets. Hence the data is not saved locally on the laptop.
      - HELM will always know about the state of the cluster, and would be able to keep track of each things it did by checking metadata.
   
  - Charts are collections of YAML files to install objects on our kubernetes cluster.
      - Charts containers all the instructions that HELM needs to know to able to create the collections of objects in your kubernetes cluster.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/93f59e50-3d0a-43ae-b7ef-669de176991d)


  - We will use 2 applications to understand HELM.
      - Simple nginx : to understand the concepts.
      - Wordpress : will help you understand a real like usage.
   
 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1512e782-f892-43a3-82db-3d0f5a09d2e8)
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/729c5ce7-beec-4f91-96b7-276d0ddd7481)

 - When a chart is applied to a cluster, a release is created.
     - Here we named the release "my-site".
     - We can install multiple releases based on the same Chart.
     - So we can launch a second word-press application "my-SECOND-site".
     - Now since there are 2 different releases, they can be tracked independently and changes independently.
         - Even though they are based on the same chart as releases, they are 2 differently entire entities.
         - You can have a release of the chart that your customer uses, and other release that is accessed by only your internal team.
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f83ff7e2-d6f2-42c9-8db7-82d309bd98ed)



  - Thousands of charts are readily available for deployment by different HELM repository, by differernt providers.
  - All of the repositories have listed there charts at a single location, known as a "Helmhub" or "artifacthub.io"
</br>
</br>
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/166bc1ad-ecb4-4c88-bf79-d2b575c78ef6)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/67fb5124-26b9-4317-8b3f-f80a80984321)

</br>
</br>
</br>

#### 3: Helm Charts :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a31e189d-1cfd-453b-820d-38c217c87045)

-  helm install hello-world, how does it knows to how to install "hello-world" application.
      - HELM does it using charts.
      - Charts are instructions manual to fullfill the request.
      - They are just a bunch of text files with a specific purpose.
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5794fb70-f75a-47a0-a610-8e478eb2ac98)

- apiVersion: v2 >> is only meant for HELM3, HELM2 will ignore this chart.
- appVersion: 5.8.1  >> it is the version of the application that is inside in this chart, that would be deployed. It is only for information purpose.
- version: 12.1.27 >> It is independent of the application version, it is helpful in tracking the version of the chart itself.
- name, description
- type: <application/library>
    - application type : it is the default used for deploying the application.
    - library type : utility to deploy that helps in building charts.
- dependencies : Dependency on other HELM chart, like mariadb chart to be deployed before the Wrodpress chart.
- Keywords : Helpful while searchig a chart in a pulbic chart repository.
- maintainers : information about maintainers.
- home, icon : URL of the home page of project and an URL of icon.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c4c673f4-6a5b-45f6-adb4-e7a95255ee58)

</br>
</br>
</br>

#### 4: Working with HELM - basics :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f64603ba-00ce-4225-b17c-4c49d02a2102)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/31af1929-9664-4cb2-8434-472ac5d8ed86)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bdfc7d92-5f4c-4d64-9c92-794df14fa8a8)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1324c80a-e186-4325-98af-1c53d4f5453b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/61103141-8914-41c3-8109-19571f1aa6af)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/39f6f731-dd92-4613-9145-aa8d694ba4d9)

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/93a14c4c-d6c0-4ce7-94bc-55fea4bfd2e3)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/602fc2eb-f755-4ed2-a723-52c729e0efba)

- A chart is deployed as a release.
    - To list all the releases run "helm list" command.
    - To uninstall the release "helm uninstall my-release".
    - To list exisintg repositories "helm repo list"
    - To update the "helm repo update" repositories, similar to "apt-get update" command. 
 
</br>
</br>
</br>

#### 5: Customizing chart parameters :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/eb8feb68-c5c9-4a9d-92bd-984114e54203)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e73724ba-2ced-4bf9-b060-144c4fc381a9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b96786b5-adc2-4d90-8f02-a5e0bcf53a74)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1e987ca5-3480-4673-b5f4-47761b8d96ba)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e9bda3c9-a696-4b87-90ed-c1f11983a9d5)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9d2f9020-38a3-4d05-a225-7813537ff774)

- What if we want to make more changes to the charts. Pull it, unarchive it and then make changes to "values.yaml" file.
- Install the chart by mentioning the directory path.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/199bd60a-3df8-4d40-9d03-95f459a5f6f9)


</br>
</br>
</br>

#### 6: Lifecycle management with HELM :
</br>























