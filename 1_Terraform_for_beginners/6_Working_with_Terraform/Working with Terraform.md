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


</br>
</br>

## 4 - Datasources :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/95f250a0-0e8c-4593-a63c-7f0d85331327)

- Infrastructure can be create from other sources as well such as Ansible, Saltstack, Puppet or manually.
    - For example if a database server is provisioned manually, terraform can read the attributes to provision the application server accordingly.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b1de2cbe-c468-4828-8e4b-fc4cacdfb329)

- Datasource allows the terraform to read the attributes of the resources which are provisioned outside its control.
    - Logical resource name : Into which the attributes for the resources will be read, with in the blocks we have arguments just like we have for normal resource
      blocks.
    - The datasource blocks consists of specific arguments for datasource and to know which argument is expected we can look up the provider documentation in terraform registry.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6c4bc6dd-c40f-4c4c-a64c-86f4f26adfa5)


    - The data read from the data source is then available in the "data" object of the terraform.
    - To use the data in the pet resource, we can use the "data.local_file.dog.content".

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3a617db9-84ee-4c5c-904d-9a670724177e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5a64b938-4021-4d36-a83a-f792e2a3523d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/62825b3c-82e9-4bb7-b0f0-ba24197ca22b)


</br>
</br>

## 5 - Meta-Arguments :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7f73ebaf-454a-4696-9a89-f7b483d5be0f)

- What if we want to create multiple resources of same instances, like 3 local_file resource.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/586637ff-2dd7-437d-a224-ebd1618fa695)

- Meta Arguments can be used in any resource blocks to change the behavior of the resources, we have already seen few metaargument like "depends_on" & "lifecycle" rules.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/325cac6c-6b8e-4c31-800a-8bae597ac345)

</br>
</br>

## 6 - Counts Metaagrument :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2b8942aa-769b-4336-85be-8089e26f5401)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ebcd59f2-24ec-4e92-aaf8-4b1874bda186)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/42c9e3a3-6eb6-4f1f-a2f6-e5358e377b7f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4d2e4301-65ef-477f-9d13-cbfa909e6bec)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d00e3f73-5108-4f8c-ab29-0c20b57125c8)

- Caveat with the "count" meta argument.
    - Whenever we make changes to the variable list, terraform tries to adjust the index of the list arguments as well accordingly.
    - And hence it destorys and recreates the resources again with the new index values.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b1c0f542-997d-4dc7-916a-e56514004978)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/037395dc-1d92-4b35-843c-b0d7fe90dab5)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dff8e1d8-1dde-484f-bb58-764912f0fffe)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dac9bf57-3a55-43e9-9d4d-b74f143f4f32)
</br>
</br>

## 7 - for-each :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3bf5691a-abf0-4053-a8b7-00e066efc156)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/af4f2e14-f917-422c-9270-44c68de9adc3)

- for-each : It works only with MAPS or a SET (as they are not sequenced data types).

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ae60e968-6125-4b91-9e13-fe78cbeaa083)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0bff43a9-ac3a-4b73-848a-a5bc36ac9d25)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8a88d35a-0d41-4b22-bc9f-60d807059a23)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e3b40789-659c-4466-ab77-a52869e2ae9c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b6ac504f-a6e7-4942-aef8-f79a1576eefa)

</br>
</br>

## 8 - Version Constraints :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c4464054-687d-4be7-84c5-cb2395999745)

- How to use the specific providers version in terraform.
    - Providers use the plugin based architecture.
    - "Terraform init" command download the latest version of the plugin needed by the configuration files.
    - The functionality of the provider plugin may vary drastically from one version to another.

- We can make sure that specific version of provider is used when we run the "terraform init" command.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f349eaeb-b36c-4977-8f21-1a1b76823eea)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d7cdfde4-4339-4952-86eb-247d41673384)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0a6a66a5-7e81-4670-b893-2aca44008a94)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1c735549-75d3-4ff9-9330-25dd188f306b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/465563c1-1641-421d-a134-c58e34eb438d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e2040ac4-2366-451f-9384-c424cdb26d16)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/55e5f4b2-f4ec-4c21-a759-fd4e7a3a0be4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/26db1876-1abf-4030-9697-9a1603ab775c)

 










































