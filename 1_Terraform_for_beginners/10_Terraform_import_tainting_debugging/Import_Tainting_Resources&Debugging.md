![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7a8bef17-ccb3-4d89-870f-af0680bed451)


# Terraform Import, Tainting & debugging :

</br>
</br>

## Terraform Taint 1 :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/395d5210-3eef-44b2-a15c-6fbbd412c1c5)


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/111ed941-3d60-4442-bf4c-3fa18465715d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9975049b-c6cf-47ff-a815-fb0890a6030b)


- There would be cases when a terraform resource creation fails when we run "terraform apply". In this case terraform marks the resource as **Tainted**.
- Terraform will try to recreate the resources in the subsequent "terraform apply" command.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e4c3d253-c673-4d42-9036-e942d6be2383)

- There might be cases where we want to **forcefully recreate** the resources. For example : if the nginx version is being manually upgraded.
    - In this case you can either perform a terraform delete and recreate the resource using terraform apply.
    - **OR**
    - You can **taint** the resource and at the next "terraform apply" the resource would be recreated.

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/97205b6b-c3f4-4070-a692-01525a798cdd)

- To undo a taint for the specific resource, you can run "terraform untaint" command. The resource would not be recreated in a subsequent "terraform apply" command.


</br>
</br>

## Debugging 2 :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9b1adfc1-0c84-425b-a963-7805282a060b)

- We might need to check the logs of the terraform.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3f7ad7e6-a105-4cf1-88c5-5e55558a67b6)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ac547018-3e97-45a6-9663-f7542c70983a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3b436664-ee19-4e7b-8fd0-3973e4fdf944)

- To unset the logs

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c2492166-ee26-48c7-a76c-9da255229280)

</br>
</br>

## Terraform Import 3 :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f94def8c-9055-4896-a8cb-de42ce16b59e)

- How to import existing infrastrucutre using "terraform import" command.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ceb81973-1bbe-4a87-bc4a-a5249ece7e56)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cb791421-aaad-499a-8f2a-d411377be5e5)

- But here the data source does not makes terraform to manage the resource, hence use the command "terraform import".

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2538ac08-cad4-449a-b742-80f6dda90026)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d342c65c-eae9-446d-8b7a-fd26fbaa4b4a)


- The first time we run the command we will see the error because "terraform import" does not update the configuration files at all. It only updates the state file with the details of the infrastructure being imported.
- So we have to manullay write the resource configuration. We have to write the empty resource block for that purpose.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cea3b942-40b9-4763-b48e-4a9b80e73be7)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0cb5576b-6102-4583-a18f-0e4c511618ca)

- Once you have filled in the required details manually, run the "terraform plan" to refresh the state.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/46bbb837-0761-46e9-a72f-b824e5b661bf)













