## 1 - Using Terraform Providers :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dac87f48-f63a-415e-9358-ecc3dfc7f66c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/09aa4c2a-91f3-4d1e-8c00-f1ff33945a0f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e93fb542-426e-4732-bb87-9cc3eb042172)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6fc29fe3-9c42-4e07-ae5e-1ca3d8acca63)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d82d0d52-7d71-4887-8ec1-856687fc8f09)

- Plugin name can also have a optional Hostname in front of it. It is the name of the registry hosting it.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b46dda23-adf7-4840-b967-ae37f0ee3ae2)

- By default terraform installs the latest versions of the plugins. But we can also lockdown to use the specific version of the terraform plugins.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a6474e36-fa62-4094-a56e-acb6639d710e)

</br>
</br>

## 2 - Configuration Directory :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2cac33a2-f8a0-4f65-b596-34e36bfe441d)

- We can have multiple cofiguration files as well.
- OR we can also have a single configuration file containing all the resource details, we generally call it as a "main.tf" file.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/76d81e2d-8037-4390-a4d1-bb5fdc84ef4a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e53288c4-352d-4df9-b07a-69e7d04518f7)

</br>
</br>


## 3 - Multiple Providers :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0357c910-0ccb-405d-8dad-c6c552442255)

- Let's use the multiple providers now, lets use the "random" provider here.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bf87a242-d3ad-4e6e-aa1b-81a41f86e76b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dbf3036b-f385-48c8-ab17-b510af550d8c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/87e8bd3e-1976-4dc1-835b-50bd75bab4b2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2cce1d40-b33a-459e-b741-ed147ebe8e8d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/36291b81-3a12-40fa-906d-3809a7ab05f3)

</br>
</br>

## 4 - Using Input Variables :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/52448261-cfd6-4f85-885a-cbb24c838c1f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2a352e67-8079-42ab-b5f8-ccc7a68f2d9a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f274e863-8b6b-4f75-b11c-3f20538c8e20)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f4cae534-20f8-46dc-897d-a82adde5b3c2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e66ec951-a6da-4c1f-bbfb-a242d19d2be5)

</br>
</br>

## 5 - Understanding the Variable Block :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/add84269-d0b4-440e-ab36-606b6d3de0ab)

- Variables blocks accepts 3 parameters in the terraform,
    - default : is the default value
    - type : it is optional, but when used it enforces the type of variable value to be used.
        Type has 3 values, String, number, bool, any
    - description : it is optional, but good practise to use it.
</br>

- Additional types of variables in Terraform.
  
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dd2e5ba4-e3e9-4c03-ac51-41a048a91da8)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/35ad7c53-8600-4834-9ffa-c4a65c48ce8d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0286fa51-561b-48f8-a9e6-695b5b28684c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/574b0fb3-a03a-4ba9-9b9e-1012f1654d5e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0395f2b5-d780-4496-8989-182c0ff159ac)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1fbb1561-35ca-4f36-a0fd-4a4e1e6cb062)

- With Object we can create a complex data structures by combining all the variables types we have seen so far.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/96c76aaf-d406-4536-b1dc-8e212e8b17a7)

- Simiplar to List, but List uses same variable types like list or numbers but with tuples we can make use of elements of different variable types.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a3250310-daca-4f5b-8618-5d24245f5cfa)

</br>
</br>

## 6 - Using Variables in Terraform :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b3a0fe7a-db12-4cd9-8005-0864c9a95a81)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6986e4d3-eecc-4db6-b7c4-0391a0d4030a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/32b68d45-85e2-4a07-ba48-cd2da35b17cd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ccdd13c2-eb41-4d8b-bd59-80ce96d8435c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bd8113ef-ff9c-43ec-8a0f-361d6d23e9d9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2574a3f7-d129-48eb-b4f7-24a1f27f79e0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/95d71d59-6c9f-4eb4-a581-1449fd45c890)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6236e1ae-692e-4ae9-a2a4-9c04d6d3a4ed)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/04154248-30c5-4e33-bd6a-20ed5fe861c2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5f3375e3-68c7-4e9f-8047-3ab58b360dbd)



































