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

</br>
</br>

## 5_Prometheus Installation systemd:

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7a3b7135-d3e3-4c55-950d-3d2905bee837)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/393a388a-0dfc-4822-8c76-d9cad49b18de)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1ba0d50b-a37a-471e-ada5-916506de1b22)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a4994fdc-a05d-4dcc-9afb-8532b3f4df62)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/27b1e024-abe0-4c41-9c9b-06a40d7da6d8)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d01f7c3d-cd5d-4895-bc1a-aa00140e622d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1dc97885-5ce8-4193-a393-994d13fda0ac)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1be73a91-0f7f-4e90-aaef-7903e4f9abf8)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1f2f4042-4d97-4416-9ff4-9a5b53f397cf)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ba46c5a9-3620-4123-87e9-819af6165b9f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0a9f4d9c-86f8-4027-990a-5a0ab6956069)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0ce93406-0e1d-4cc3-8315-e5f8c530ef39)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0670e8f1-b162-4255-901a-f486b48f6304)

</br>
</br>

## 6_Prometheus Installation Demo:

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/62c0222b-c06f-4c5d-8937-022e9909a539)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c097f590-1699-45af-9ecb-f79fd98c4e5b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7fb01f59-3894-4ad0-a379-4c4ef2e225d9)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/303955c0-f6d6-4e9d-b690-5a54b967d648)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f6563d2e-81ff-4b55-aa17-5e4a5865d286)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/23ebb7a8-d1ba-4308-b4d7-3bb44fd0f863)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/68789219-942a-405a-82b0-787e73508a26)

</br>
</br>

## 7_Node Exporter:

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8f196945-5f23-414f-9293-58b0b7383f0e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/220076fb-d944-4e97-b46b-f3dc51550a82)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1db40877-f127-4dae-b9de-05e55fa7817c)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bd95a2e1-6266-45ca-8c00-b06868cd9834)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8402b9b4-a270-44c4-b442-21d5318aba5f)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cfc71319-87cf-458c-bbe6-f5c0449f7ade)

</br>
</br>

## 8_Node Exporter systemd:

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2cf99304-3249-4430-9240-49ae6488091d)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/18ec9f86-ff65-4e82-bb2e-1e4e5d91204a)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/739c7779-77ee-44a6-8105-9d91a3c38574)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/57024f21-9d28-4a72-854c-5d42fc24113b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8a6077d8-f666-43e2-979d-7715dcbca6fb)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/82f93c7c-f813-4b64-8e5f-8753a5d94659)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/61a2018c-948b-4283-898c-fb781e6f8783)

- Demo 
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d0278f52-576d-43f2-b799-ea137898ad44)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/64690823-8487-4e38-9835-f3c4d0395312)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4a064c9b-2e7f-43c4-bfb2-420dd25cec74)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ac7c4ca4-9ab0-43c2-bf6b-5659fbdf8c08)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/7c903125-3982-49d6-bd3f-3e59601876af)

</br>
</br>

## 9_Prometheus Configuration:

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d5d83380-0f9d-4321-b698-7af6a7ef8a94)

- Add node exported to the prometheus configuration, to enable monitoring of the prometheus target in the prometheus server.
- Prometheus server should be aware about all the exporters.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/499149d2-8d2a-4d8b-847e-6a070729f6c0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/9ed83296-62fe-4bf2-96b6-25213d38a7e0)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a0c3a61d-78c5-431c-9a1e-8b1787da0874)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/c015a557-2c86-4e3f-9019-d89ae606c97b)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/d89280d6-078c-421c-bf58-201ec21f2b37)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/eacd8b77-4045-4855-b2c5-ec0540bbbe49)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/eb6c40a0-e013-44ca-a724-88aee2e91e38)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/55e54639-64b2-4c74-9baf-782720acbf14)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8d0c4396-8eeb-4bce-a743-b406063d8fc1)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/95f911e1-d3e9-4bb9-83d5-335990e0a9ad)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ce64fffa-51d8-43b3-91f5-cd366a576d2d)















































































