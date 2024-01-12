# Terraform Provisioners :

## 1 - Intro to EC2 :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7e5875e9-ad7d-4995-b247-b9725210f26a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c16da4c0-3f6c-4efd-8e35-ba42c46a733b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b36ea65c-5e45-4052-bd83-e45292bebd29)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cd72e4c8-8640-45be-b9c0-8cf8c43c3732)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dd6a7f7f-a7e1-4507-a697-780f421602f0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/61e222f0-c213-484a-aa02-5fcbfcbd1b16)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b5691f65-6ba9-4366-99b4-7c14bed84ce5)

</br>
</br>

## 2 - Provision a EC2 :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c43c28c2-3045-4a1b-b424-e8c56b402a00)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ebbf87bb-50d7-4a77-ba44-f96311249db2)
</br>
</br>

## 3 - AWS EC2 with Terraform :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/589cdefa-4f46-4a8b-b7ee-adc8b4672558)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/09251a71-ca54-4867-b60a-c7c0c7ed9a5a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e3b9296c-1ca8-40ae-a96e-30642fcdee32)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c2a8d591-97c1-4d47-a11b-659fb32a1a52)

- How to mention the keys :
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/13f1ea1a-1454-4809-964a-3940056d46d6)

- Networking part :
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/93577142-81a3-432e-87c1-1b9d9e24f011)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8bc0ef9f-282b-499e-b062-82033651333b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cd5a101d-aa0c-459f-aee3-ed6233a5078c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8d3dd658-8327-47c1-abb1-a6da84a0c530)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5131d90b-e62e-449b-91fd-75eaf41c98bf)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/15e96185-36bf-47e7-b40a-4e00c8cb70c6)

</br>
</br>

## 3 - Terraform Provisioners :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bdd7e6b2-b144-4940-b80a-65c51fc272d8)

### Remote Exec provisioner :
</br>

- **Provisioners** : Provisioners provide us a way for us to carry out a task such as running commands, scripts on remote resources or locally on the machine where terraform is installed.
    - For example to run a bash script after a resource is created we can make use of "remote-exec" provisioner.
    - We can pass in a inline script as below.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d6582cb9-4bfc-41c6-a16a-8446143b9e1d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/89053127-4bc4-4e35-9c51-e7be90182b7c)

</br>

### Local Exec provisioner :
</br>

- **local exec provisioner** : Is used to run the task on the local machine where we are running the terraform binary and not on the resources which are created by the terraform.
    - This is specially handy when we want to gather the data and want to write in the file locally.
    - for example : if we want to write the public IP address of the EC2 instance locally that was provisioned using terraform in /tmp filesystem.

- **Create time provisioner :** By default provisioners are run after the resources are created.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/24aa9aee-9c16-45f0-b980-81f179ebe8ca)

</br>

- **Destroy time provisioner :** Make a provisioner run before a resource is destroyed.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b8a8e6cb-3941-45e8-b14f-e6dfa9c0bf53)

</br>
- Another default behavior of the provisioner is that, if the command or the script fails then "terraform apply" operation also errors out.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e7602aad-d8fc-4569-b059-440ba6d0b2ee)

- We can avoid the failure using below block.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0b73b001-5621-4595-95a9-203069b3f18f)

- **As a best practise avoid using provisioners, use it only as a last resort. Try to use options natively available for resource types for the provider used.**
    - For example you can use "user_data" block as below.
 
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2bfa5684-9b14-4098-99e0-76b2bbd3e80f)


</br>
</br>

## 4 - Provisioners Behaviour :
</br>

- The remote-exec and local-exec provisioners we use, run the task when a resource is created. This is the default behaviour and is known as a the creation time provisioner.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/aca4db70-e221-4066-b603-d62c774fd35f)

- Destroy Time provisioner : Run a provisioner before a resource is destroyed.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3c85f0be-51f0-44de-9169-b17b6d559aa2)

- Failure behaviour of provisioner :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/841336ed-6223-4b83-af31-83f6f6e9a217)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6f6c772a-b0e2-4ae7-89bd-7e13af56ab86)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3ed7c667-df08-4d3b-bb0e-b9be8c8e8f7d)

</br>
</br>

## 5 - Considerations with Provisioners :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2e310bb8-0e0f-434b-ac50-9298428b0d43)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c0677dc1-a38d-42ff-8d2c-49d1b07cdb2c)

- Terraform recommends to use provisioners sparingly.
      - Making use of provisioners increase the complexcity of the configuration.
      - A connection block must be defined for some provisioners to work. This means that network connectivity from the local machine & authentication to the EC2 instance  must be established before provisioners is run. **This may not be feasible always**.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f77462cd-f869-46df-a478-526a74470abe)

- Better use the user-data resource native provisioner.

  

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/04064a53-e85b-4b35-a87d-83d4f8c9a1f5)


































