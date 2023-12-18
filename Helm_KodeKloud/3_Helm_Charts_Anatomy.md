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

#### 4 : Conditionals, With Blocks, Ranges :
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

</br>
</br>
</br>

#### 5 : Named Templates & Chart Hooks :
</br>

- Named Teampltes :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dc73eb6f-f34c-4676-be35-e3953f693ada)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d1af5045-e952-416d-a573-d698013f32cd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ac1e0a86-e593-4c54-8af3-1eb4308579de)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/65473f10-9ea8-4c6a-94aa-6bd39abfcefa)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a87b6bcf-0414-42c7-abf8-fe05a2776f99)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5fa7fe8d-58ca-4ca4-b467-9d9f75f0c904)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3b539da8-231f-428b-88e4-68c9732aa8bb)

</br>

- Chart Hooks :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c7358e61-3a2e-4e0e-8c0d-6a7472dd3b1f)

  - We might needs to do some extra stuff too, whenever we do a "helm upgrade" a database backup should be taken before the upgrade.
        - or sending an email upgradation before actual upgradation, etc.
        - These extra actions can be implemented using the "Chart hooks".

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5f890478-32de-4210-8df5-35738591e19b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/23dc2750-6a47-4912-bee3-50f1693d77f1)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/525ff3f3-7b78-4097-8325-1b43f9dff1fa)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/807476b6-feca-48d1-8e4d-5b73c9a33a4c)


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/107a572e-4486-4563-8e73-e5814f0ada40)

- For running a script only once, we create a "Job" instead of "Pod".
- similary we can use, ppost-upgrade, pre-roll back, etc hooks.

</br>

 ![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5462eb85-f75f-4e5e-903b-63215dcae348)

- Multiple pre-upgrade hooks can be used, but we might need some particular order, likfe email annoucements needs to be go first, then  side-wide banner need be displayed and then finally the backup has to be started.
- For this we set a wegiht for each hooks/jobs, in order which they should be configured. The weights can be configured from negative to positive.
- HELM sorts them in the ascending order and executes them in the ascending order.
- Multiple hooks can be placed with the same weight, at that time the hooks would be executed based on resource types and other criteria.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/401e696a-006d-4b76-8bb5-abbd295144ce)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ef1a4089-1632-40b6-b083-9417874fed3f)


- The job remains there once it is executed, to clean-up we can set up the hook deletion policies.
- "hook-succedded" in this policy hook remains as it is if the "backup" job fails, we might need this resource for debug purpose.
- "hook-failed" in this case the "backup" job is deleted, even if the hook fails.
- "before-hook-creation" this deletes the previous hook resource before the new "hook" is launched. It tries to avoid creation of duplicate objects.

</br>
</br>
</br>

#### 6 : Packaging, Signing Charts & Uploading Charts :
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4b1ebb41-b1f7-4974-b55f-3a5e0e8124a7)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/489fc822-5eb6-48bc-9c82-f0b1b0d162b2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e8a8e672-017f-405b-9bcc-0d8ca5eb48e5)

- We might need to sign our chart, to avoid the hacker preventing from modifying the charts.
- "Public key" is used to make sure the Chart is signed validly.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/67acd6a8-1353-43ae-8afd-514acfd9553c)

- We can use "gpg" quick generate key to sign a Chart.
- In production "gpg --full-generate-key" command is used.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a5fac6e0-0394-47ac-9765-b4e69278dd78)

- We package is using "helm package --sign" option.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/07ae8931-e7e6-428d-a3ab-f44350457274)

- Addition file "provenance" file is generated storing the SHA hash.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b16cf514-ed9d-42f6-9db6-0cdf977c7465)
</br>
</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a96ecc9f-139f-4846-9dae-eb676d53db4b)

- Uploading the Charts


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/6fd23655-0949-4dc2-a08b-0edacea3ff48)

- "Index.yaml" file contains details of all the contents of the Chart.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1abf6c19-f7da-4b6e-b860-557bb8573d02)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bf2112f1-de4c-426d-8e41-126f1e76f5b3)

- To generate the "Index.yaml" file, mention the URL of the repository to which we would be uploading the Chart .tgs file to.


![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3a171734-4c7f-4f61-874d-56671ee3ba18)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cbbe9881-f4eb-4982-af16-e93414df8e75)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5d9ea6f3-fd80-4c18-bd93-919f4a4baccf)












  










 



  


















