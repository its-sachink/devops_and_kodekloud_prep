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
















