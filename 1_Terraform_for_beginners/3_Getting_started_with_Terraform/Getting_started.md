![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e04a6797-37c1-45e3-9b3b-7f093c4ede52)


##### Installing Terraform :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/66641f46-16ff-4369-9329-d0be26ecd68e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4e48b1d1-5d9b-4714-bd0c-dd02a524c7b2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/86618d71-5b6a-49df-9365-1be9f574a043)

- Resource is a object that Terraform managed like a file, S3 bucket, EC2, DynamoDB, Azure, GCP,etc.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a9438ec7-15fd-4ec8-bc7e-2b71a234071e)

- We will for now look into 2 types of resources,
    1) A local file resource
    2) A random Pet resource
</br>
</br>

##### HashiCorp Configuration Language (HCL) Basics :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e41c2361-1e30-47f4-a79f-3c5c2996b905)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a991e3fe-43a4-488e-ba0d-a8e0cc7df53e)

- HCL syntax
  - A block in terraform contains information about infrastructure platform and a set of resources within that platform that we want to create.
  - For example create a file with in a local system.

</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/50f5c161-c939-47f0-bb0a-5a1a4237a490)

 - Block == resource block == following the declaration we have the resource type that we create, here it is "local_file"
 - Resource type == It provides 2 bits of information, 1st the provider of the resource which is local here, 2nd the type of resource.
 - Resoruce Name == The name of the resource.
 - Argument == we provide them in Key value format.

Few more examples of the resource blocks is as follows,

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7a2dcdfd-3838-48cd-8026-b8c0037b123c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3e998d64-60c6-4fb7-a8dc-8b1cbb7a8cb2)

</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e2240f2d-0c0b-4d17-b5dc-6ac8b90c1360)

A simple terraform workflow consists of 4 steps,
  1) Write the config file.
  2) Run the "terraform Init".
  3) Review execution plan using "terraform plan" command.
  4) Apply the plan using "terraform apply" command.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3af97d3a-8571-4dc4-8c83-77eec58b4053)
- terraform init : It will download the required plugin to create the resource type declared in the "local.tf" file.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c5621cb8-b6e3-4732-8e71-1de2fabbf6f1)
- terraform plan : To see the execution plan use this command, it shows the set of actions that terraform will perform to create the resources.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d44025e2-3514-468f-8782-4cc531993462)

- terraform apply : it display the exectuion plan once again and will ask for confirmation.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8fe82ed3-08a4-4875-afa8-b563a49ea831)

</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0dc1135a-e8e4-4aca-bf27-f3e8647dea08)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ba36baa8-07cc-47a2-8aec-acf0769ff3fa)

</br>
</br>

##### Update and Destroy Infrastrucutre :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/71972858-3405-4db1-bc50-d038423eca14)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6aa4a1bc-5deb-4a33-b88b-86854d49d042)

- Here Terraform will delete the resource and will recreate the new file resource using the new permissions.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ee8f697f-cded-44b3-9a18-4965409ca392)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7595f655-c77f-49e9-9879-8cf233550373)


##### Labs :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0b210741-001e-4c2a-a20c-5f39dd3c6581)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0f2d8146-c80f-4398-a383-d32f8516c09c)








