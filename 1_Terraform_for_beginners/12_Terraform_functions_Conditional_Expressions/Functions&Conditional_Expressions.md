# Terraform Functions & Conditional Expressions :

</br>
</br>

## 1 : More Terraform Functions
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cee6fe47-edfe-4222-a923-5a88ec5b2881)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/efd17f41-5aa9-4fb2-a11c-0d186334b610)

</br>
</br>

### Interactive console :
</br>

- Terraform provides us with the interactive **console to test the functions**.
    - The **interactive console loads the state associated with the configuration directory by default**. Allowing us to load any value that is currently stored in it.
    - It also **loads variables that stored within the configuration files**.
    - This **allows us to experiment with the functions and interpolations** which can be later used in the configuration files.
 
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4bd4766d-57fa-4e9a-b703-7ea0b8647f35)

</br>
</br>

### Categories of functions in terraform :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2b834040-1740-4d32-9f15-75b393bc045a)

- Numeric functions : Are used to transform and manipulate numbers.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f7fddc50-8ca0-401b-b0dc-c34e9750bf7e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3b3b5b71-6b03-41c4-9385-215ce71991c3)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/fad2604a-50d3-4ee9-9f7c-1f1d615d7647)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d0153d5b-5e25-4fd6-9b54-4645c675fb8c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b8396941-5068-40cc-a5e7-6dcb7706fd02)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/859df173-21ed-49d0-9dc8-0da5ca5a56c9)


</br>
</br>

## 2 : Conditional Expressions
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/fa6a1f99-5663-42f3-910a-15777402b051)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/407a1a64-aa90-47cc-b289-25c594556172)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7dcfbee3-8c04-4b64-bce6-90ed8622ecc4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a911bdb1-941a-4e4e-a566-e46b934e6cca)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/909d3ab4-1c6f-4207-be59-1f513c2439ba)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c5327f91-76c6-4356-a997-22e480cdcc0b)

</br>

### How to use these operators in terraform :

- Consider a usecase where we want to generate the password of minimum 8 characters, if the lenght is less than 8 then set the default length as 8 characters.
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b65e2a85-df4f-456c-b6fa-cd234f714563)

- This can be done in terraform as below.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6a8b4dc1-4034-4de3-9425-f584ffc2e0f1)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/55d57d8a-50ab-494d-a336-69b457c37fb7)

</br>
</br>

## 3 : Terraform Workspaces (OSS) :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b6cc710e-39e4-4170-b887-f1125e484fa5)
</br>

- We had a one terraform state file per configuration directory.
  
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/59455a07-c517-45ad-bf41-302b8e517f2a)

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7c878828-2d52-4471-afe3-d0d238adf8b5)

- What if we want to have ec2 deployment in ProjectA and same deployment in ProjectB with a different AMI Id, here we would copy the configuration files generally with a change in AMI Id.
- However goal of reusability does not satisfy here.

</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e65f36a7-6688-468c-8023-f98ce1f66fad)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/069472c3-45cc-4993-b8b2-efa086b64c83)


- **Workspace** : Terraform offers a feature to reuse the configuration files within a directory to be reused multiple times for different use cases, such as creating a ProjectA & ProjectB within in a same configuration directory.
      - With workspace we can reuse the same configuration directory to create multiple infrastructure environment such as ProjectA & ProjectB.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5b6fea92-07c6-4793-bf14-c60adc3a7b96)

</br>

- We remove the hardcoded values and configure that as a variables as shown below.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/09049dd2-7c4d-4b73-99ec-2d0da7e4e9cc)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b729d28c-7515-488a-90e0-9705d2e4f6f6)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6ca2caa4-788e-4d0f-bde5-ab04ecab3ddc)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/318531ad-0403-4c4d-b9bf-253bc42f0292)

</br>

- For each of the workspace it creates a 2 different state files.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6cffaff6-7418-4ac4-8c9a-d3407846127e)






















