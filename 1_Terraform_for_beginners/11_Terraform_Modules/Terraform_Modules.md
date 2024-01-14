# Terraform Modules :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d0f47937-1c63-4f44-83ee-d9776fe6ff08)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/be04e777-71a0-4d92-9cd3-bf0cc9251ba9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/da5b64a3-8abf-4185-9e21-ddc9f32a2ab2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/96c51731-e500-4857-bb92-f992589bc568)

</br>

### Modules : Any configuration directory containing a set of files is called a module.

- As shown below, the directory "aws-instance" contains a configuration for the resource aws-instance, this would be called a **Module**.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/41b391ab-81da-4c63-8316-db6b5529fa16)

- In the below configuration, the "development" directory becomes the "Root" module as we will run the terraform code from this directory, whereas the "aws-instance" would be called as a "Child module".
    - The path can be relative path or the absolute path.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c71a4c47-2343-42b6-8b28-288c02554280)

</br>

## 2 Creating and Using a Module :
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/13fa9a81-a3d1-46db-9b86-85a8c9f49278)
</br>

- Consider the below architecture

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4f705ecf-0873-44d1-83ef-b4d6fe58c541)

- The idea here is to use the reusable terraform module and deploy the same stack of resources to different countries.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8b44a983-68d0-4240-acd1-9053dbeccf02)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/604e43d8-228e-4f6b-b421-c97062699749)

- Now lets deploy this instance in the **US-East region**.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a77890ee-c054-42ab-94d8-ea649faaa033)

- The **hardcoding** below is being done to ensure that the configuration remain same across each of the resources.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4291cba4-f35d-4257-9dd4-5241fc18821c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/df9147a9-42b2-492c-8c40-0505b1bb1573)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7e53c95a-eb0a-46cf-bb9e-e45fc068d2ce)

- To deploy the same stack in the **UK region**, **create another directory** called **uk-payroll-app**.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3fca0dbd-5858-435f-87b5-6466fa856ccc)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7467a66e-5c1d-4c2e-ab71-d9a62316f802)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/33b46475-bf93-4446-ac2b-a2d5e9013a74)

</br>

## 3 Using Modules from the Registry :
</br>
</br>

**Local Module** : Reside in the local machine from where we are running terraform.
**Terraform registry** : It is also used to store the Publicly sharable modules.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1075814c-7c2c-4de9-9a4e-23bfdebccf03)

</br>
</br>
- The **Modules** in terraform registry are group based on the provider for which they are created. They can be categorized based on 2 things.
      - Verified module : Tested and maintained by Hashicorp and has a blue-tick on it.
      - Community module : Published by users in community but not validated by Hashicorp.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0251cd70-ebf1-4eca-8955-a07f3c7cbe0c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c9f4e70d-f043-43d5-84f1-4e67c2969cd8)
</br>
</br>

### submodule :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1b136ee5-cfc5-46d3-8a72-fdf842ab75c7)

- Usage of submodule :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4d7c1910-4210-4e1c-bd32-a1f97b7e151e)

- **Important** : It is always a good idea to mention the version of the module, if we don't specify the version then in that case terraform **will always download the latest version** which can introduce **undesirable** results.
- Finally run "terraform plan" and "terraform apply".

























