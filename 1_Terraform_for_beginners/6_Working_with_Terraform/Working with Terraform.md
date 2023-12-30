## 1 - Terraform Commands :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f939e1d0-16b2-4d80-80ce-fb1bfef70a54)

- Terraform validate : to check if syntax is correct or not.
- Terraform fmt : It scans the code in the current directory and formats the code in the canonical format. To improve readability of the code.
- Terraform show : Prints out the current state of the infrastrucutre as seen by terraform.
- Terraform providers : To list all the providers in the configuration directory.
- Terraform mirror : To copy the providers from current configuration directory to another configuration directory.
- Terraform output : To prints all output varaibles in the configuration directory.
- Terraform refresh : To sync the terraform state with the real world infrastructure. If there are any changes made to the resource using manual update. the terraform refresh command will pick it up and update the state file. It will modify only the state file.
- Terraform graph : To create the visual dependencies of the resources in the terraform configuration or in terraform execution plan.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5b8dd079-2c6c-403a-b6cd-737bf0a3f709)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a00f3754-d3c7-44df-a2e1-8bc5ba15c4e9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/deee5b3f-9451-4be3-807d-f593c2e06548)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/81d60f4a-be00-4b6f-834d-4cbc52c024c7)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7a90f8ca-c979-4d04-a6ae-e444446ab4fd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0d2241c4-8353-4da3-9367-77e90022d541)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/46b256bd-dda9-482d-ad7a-3b80edffcf12)

- Pass the above dot file to the graphviz tool to generate the graph. Open the graph file in the browser.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bcf2ea87-6ac1-418b-9556-3b15ad361f54)

</br>
</br>

## 2 - Mutable vs Immutable Infrastructure :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7540406a-b8cf-4a95-8828-2a730a31e44e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4c688bbe-271b-40d4-94a1-ff2cf8f59910)

- While upgrading the nginx webservers, it is called as a inplace update. This is called a mutable infrastrcuture. (like for file it directly replaces the file with the contents).

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7d3e2ce1-f14e-481e-9d96-91d4ec50ccbb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a03fc2d4-356b-42d4-a432-8bc7cf687633)

- Immutable infrastructure : Something which cannot change, we cannot carry in place updates of the resources any more.
  
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5045d107-9041-402e-9e05-c1704cb20c0f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9acd0f21-ab42-4467-b159-34a4ccc6beb7)

- What if we want the resource should be created before destroying the resource. How do we do that ?
    - This can be done by making use of lifecycle rules in the resource block.

</br>
</br>

## 3 - LifeCycle Rules :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6044c48c-41c6-4cb4-b967-064b0b74d985)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e075b876-8ab1-4633-a80b-c20d4fe8edc7)

- Create before destroy rule : Create resource first before deleting the older copy.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/665882d5-8ed7-4acc-9f5d-3e95b0386456)

- Prevent destroy rule : Don't delete the resource.
    - Useful when you don't want resources to be accidentally deleted such as PostgreSQL, MySQL databases.
    - The resource will be destroyed in "terraform destroy" command.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e81bbe6d-e45a-48da-8d0a-197ee7671928)

- Ignore changes rule : It will prevent a resource from being updated based on list of attributes that we define within the lifecycle blocks.
    - For example if we manually change the Tag's manually then terraform will try to make it to the older state again.
    - Suppose we want to ignore this change which we had made manually to be reverted by the terraform, to avoid making terraform to make these changes add the tags to the "Ignore changes" rule.
    - Ignore change tag accepts the list and any valid resource attributes which you want terraform to ignore.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3ddc58a6-7e22-4280-b88b-e1464ad8af92)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5358da59-ecad-4a88-9ca6-e95f330a5c2a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/27f1d2a6-9970-47e4-b097-c8f6349f663b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7784d393-1980-41dc-8958-593c01b1a4f0)




















