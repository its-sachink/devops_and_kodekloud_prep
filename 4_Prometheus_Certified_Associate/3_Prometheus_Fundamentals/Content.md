# Prometheus_Fundamentals

## 1_Prometheus Use Case :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4d913b7e-444e-44a4-9285-5a747ec61d23)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0c7bcea8-06a7-41aa-921a-0ac20ea482f5)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1caa0698-f035-4701-951a-b29e15464b55)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/40d181e4-ca64-4769-a5b2-235c30b2596b)

</br>
</br>

## 2_Prometheus Basics :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3cfa2d24-c743-487a-95f2-020c993e2adb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8d2b0737-c060-4e6e-a3d8-974ea2977777)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3854a093-a22b-4538-9123-a3046ce7c110)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d92606c2-21ac-4bcc-9762-d358ee329611)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e61958d6-997f-4d5a-8a0d-26fb9352bd5d)

</br>
</br>

## 3_Prometheus Architecture :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/dff01a9b-1080-49d3-9822-7478dd553a69)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/998fb7aa-4255-46f5-b2f1-81ba37d3597c)


- TSDB : Time series database.
- Exporters : Are responsible for taking the internal data and converting it into a metrics that prometheus will understand.
- Short lived jobs : For short lived jobs you have to PUSH the data.
- Service Discovery : Provides a list of all the dynamic targets to pull the data. This service discovery updates the configuration of the prometheus to dynamically update the Promethues targets.
- Alertmanager : Prometheus generated the alerts but alertmanager is responsible to send the alerts via email, slack.
- Prometheus UI : Use the PromQL to query the data and populate the UI.

</br>

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/672297c5-67f7-468e-9784-4de721e1987b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a97fc517-159d-46e2-a0c4-768778517d8d)

- Exporter : It is a service that needs to be installed in the target, it collects the metrics and converts it in the format that prometheus understands and then exposes a /metrics HTTP endpoint where the promethues is able to pull and scrape that data.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8d778169-7ae2-4df1-8530-4036cdcfdc69)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ad873484-fa1e-4d43-84c1-c99eca5b9922)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4ea43f39-1f40-4687-9adf-1595f0bdf01b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/3f599657-9e19-4a6a-b52c-1f6292e42a2a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e036e19f-1e0e-4832-a424-b6aec52d93e0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/16a7a0d6-f4b0-47f4-8a4e-bda55d95b8d5)

</br>
</br>

## 4_Prometheus Installation :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7d0a02e7-f6d0-465a-ad8f-bc3f7dbfda09)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1560b6f1-e107-4b29-bec9-558400c158f3)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5033517a-9130-404a-99b9-0d1f5c9d6dbb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/be6fc52d-e6fd-469b-9edd-9986aeb758a1)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/69eb7fd9-5007-4b6e-95bc-25bce129fadd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/07f2531e-3d16-40a0-8c5a-2a9499f510e3)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/fc47921f-077a-4da0-821c-5a2affb2a574)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/06cf4483-ef61-42a8-9f74-ff9ae5b7efd9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/53c8f1bc-17cc-4237-b41d-69bc1507dc63)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8f2ac81d-6ce1-415a-ab07-cbd1965ac74b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/da4aa0b2-bbfa-4da3-b597-c78852fd044c)
























