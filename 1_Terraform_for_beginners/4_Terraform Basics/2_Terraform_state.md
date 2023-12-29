## 1_Intro_to_terraform_state :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c1562b18-5da3-428e-bf93-b3315ce6f54f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/42af076a-33cb-4bd4-9d2a-fa44e9d091b6)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/baecfe5f-6190-4ebd-8378-68f26022e406)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bcf39394-06d4-419b-9315-455f99c9b33b)

- State file : it is the JSON data strucuture that maps the real world infrastructure resources to the resource definition in the configuration file. 

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8385f9d1-01cf-43e4-900e-a178b7662242)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b0012a63-8274-4408-9689-60b314951b47)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/20e9c5c9-1e7a-4d5c-afc1-78e7dd53d2d4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8109e1b4-d334-44ec-8284-164a2db9c940)


## Purpose of State :

- Each resource created and managed by terraform would have a unique-id, which is used to identify the resources in the real world.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0f41ffda-6c7f-416a-bc77-a1442ad935d5)

</br>
</br>
- The state file also tracks metadata, such as resource dependency. (implicit, explicit dependecy)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/11cb7c08-87eb-4cb2-adce-5c3a29b8a75b)

</br>
</br>
- It also tracks the order while destorying the resources in the state file.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/94c84e9b-c70f-4148-a19a-697fefc3a1e2)

</br>
</br>
- For larger infrastrucutre, the terraform pulls the information regarding resources from the state file. Also while running "terraform plan" command you can avoid refereshing of the state file using "--refresh=false" flag.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/adc790af-dec9-4635-8b80-993ea1c92010)

</br>
</br>
- While working as a team, all the user should have a latest state data. In such scenario save the state file in the remote data store, rather than relying on the local copy. Shared between all the team members.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f69e076d-8853-41ef-ad67-2c4d4a105ade)











