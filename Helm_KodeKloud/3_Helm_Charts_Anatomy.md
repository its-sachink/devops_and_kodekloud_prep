## HELM Charts Anatomy

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/002a0a7d-bbfd-4ecf-ba14-17549ce4aedb)
</br>
</br>
</br>

#### 1 : Writing a Helm chart :
</br>
- They are similar to installation wizards on the operating systems. They act like programs to install various kubernetes objects for the application.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8a72a27a-2428-454f-94a0-a117c7e4dc9f)


- They can perform extra stuff too,
    - such as whenever we do a HELM upgrade a database is automatically backed up before the upgrade happens.
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2034dc36-c630-4bb5-ba97-c539a7788655)

- HELM chart is a directory with a specific structures.
    - So we have to create a directory structure first using    # HELM create chart_name
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9e1a62e9-64a0-44f9-aa8c-0c1f10bdb341)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9c30dc74-9835-40b9-8431-27551efc3e76)

- Add some basic details to charts in Charts.yaml file.
- Emptry the Teamplated directory.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9fac0703-e8a6-4b2c-92f3-e1b4c6a469bd)

- Move the service.yaml & deployment.yaml file to the templates directory.
    - The problem is now that we have a static values defined in the service.yaml & deployment.yaml files.
    - Trying to install another release with the same chart will fail, saying deployment with the older name already exists.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c52b22c0-3a6e-4bfd-94fa-fe1d36d973c0)


- To Solve the above problem we templatize the HELM deployment, we use the HELM templating language to tell the deployment that the name of the deployments should be based on how the user choose to name his or her release.
- So {{ .Release.Name }} should be the deployment name.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/58da118a-1d31-4e5f-a12a-7203b09933a0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c4c456c0-6351-4b81-a600-7e8d26a7c1d3)

- Similar to release name, there are other objects as well such as below.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/08ccb2a8-ee33-4f61-8ea2-cdf12e86fe2f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0ed82025-2001-43cc-8fa1-fc648068b187)


- HELM doesnot allow us to perform deployment of 2 releases with the same name.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/77828afb-43c8-44d6-83dd-dba4583eb98b)

- Anything defined as values should be passed in as a values options or a set option in the HELM chart.
  OR
- We define in the values.yaml file.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b2dc80e8-201f-4eea-bbfa-36549f08145d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/97c50e5b-fa60-418c-99fe-6ef62b231bca)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/54c6c016-d034-4290-9db1-2a143f95dc45)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a53e0f68-980f-4326-b155-883c1569d93f)

</br>
</br>
</br>

#### 2 : Making sure Chart is working as intended
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9cc6ec8d-bdf0-43ce-bbed-0cc4f9a86df4)

- 3 ways to verify HELM charts before installing them.
    - Lint : Helps us verify that the chart & YAML format is correct.
    - Template : Helps us make sure the templating part is working as expected.
    - Dry Run : Helps us make sure that the chart works well with kubernetes itself


##### 1 : Lint the files

- There could be few Indentation errors or a spealing errors as well.
- 
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ba3897e2-4ea0-4c48-beea-addcdbcfcad5)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/96dc7577-9f0a-4d67-96ec-f6f656f8dd5d)


##### 2 : Validating Template

- # helm template --chart-name :

  - It renders the chart name template locally and displays the output,

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e5b3c400-4d45-4120-9110-f822fcad5b16)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c099966d-9da0-4c76-b70f-3ee5854285d4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/154313f1-18bc-4bdd-8d10-a6762108e008)

- If there is a intendation issue or malformed, the template command would fail without giving much details for which you will have to use the Lint command.
- In that case if would help to see how the YAML file was generated to see the intendation issues.
- To see the YAML file that generated error use the --debug flag.



##### 3 : Dry Run

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6d434be7-96e1-4d7e-906c-e889245f90e1)

- Now there might be error in the kubernetes manifest file, like we might have mentioned container instead of containers as above.
- For this we need to run the --dry-run option.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/453b69f7-c900-40e7-9be9-8303a5a3c564)

- After fixing the issue as above.


</br>
</br>
</br>

#### 3 : Functions & Pipelines :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6468ebd3-78eb-435b-8ae7-e4fb80f66e84)

- There might be a case where user might not have provided the "nginx" image name
- In that case we might need to use some default value, for which we can use functions.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0ca2a9a4-f193-4311-a061-b60a88f9d98c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0f5bc065-3da4-492f-a479-5403609e8afd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0d641950-5ad3-4621-b196-b6202c1f86be)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e395cd72-8ee3-4c69-a315-aff511f4471b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/fe56fdd8-e306-4c50-a4be-aebcb17a2ab4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/15f21443-e225-4c8a-b84d-f9acabb62c08)

- Pipelines :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a774fc8a-517e-4742-aeca-8fbfae136205)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cc1421ba-21bd-438d-aff6-9ab3094d6682)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0f8631ea-b81b-41c4-9900-d952aab2839b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/11514b77-5474-49ef-ba0c-7f83b2c86747)


</br>
</br>
</br>

#### 4 : Conditionals, With Blocks :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e6045d4d-acbe-45c4-86bd-ae7a9b14c445)

- What if you want to conditionally add the lines.
- For example if value is present in the values.yaml file then populate the manifest.
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1e5ca677-bde0-4af3-b7c6-db5676c743db)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b02baf69-6c95-4b18-8bc5-7b500fb055b2)
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6304065b-3681-4f06-b964-1b080f30ee38)

- Only if the "orgLabel" value is present the values.yaml file then populate the service.yaml file.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3632cfd6-f123-475e-950d-28e8874580a2)

- Remove the empty lines, white spaces using the "-".


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/aa586d14-b033-49d7-8c10-b1b7f91bb812)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e7322ec5-6cef-4c4e-83f4-9cc2c1b1ab96)

</br>
</br>
- Common use case :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7fe35130-41f4-43d8-b78c-5b62350e0cc7)

- Common usecase of conditional is to create the objects of certain kinds or not.
</br>
</br>
</br>
</br>

- With Blocks (scope) :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4bd5e5a9-8e45-4fc4-9b1a-a67636317d19)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/64458e02-eb6e-4caa-841e-0d9f902323eb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/11411de2-3206-4fec-a8c1-5845adce7840)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7ec60fed-626a-4b76-abde-ba9a90aac9f6)

    - To escape from the scope and to refer to the root scope, we use $ sign.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/99097ff7-fe63-424e-b756-4c62e07e14b7)

     - We use the Root scope using the $ here.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f71b3d3f-ad65-45a6-b7aa-bf5482a5500c)


- Loops & Ranges :

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3cc0bbc3-92ee-4ec6-a7e0-4b0d525a369a)

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dd5fa8f2-f890-4a9c-ac21-51fd008a9bab)

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ef30c4df-0036-4de9-94b1-e67741b0af90)

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9349632c-d205-467e-945b-34d426952d9c)



 



  


















