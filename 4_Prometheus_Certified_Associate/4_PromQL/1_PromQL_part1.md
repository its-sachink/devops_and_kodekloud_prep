# PromQL

## 1_Introduction :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/90d90b4b-a07e-4709-8b78-1705fe53aa17)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a83c3ab8-0a10-47be-adfe-0be7156901d3)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/397e9b4c-d38d-4285-90dd-3fdbaff2e638)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8cc0c030-43a0-4de1-b170-40a14784c6e5)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/bc9db965-14cc-4d14-865f-2871e6334528)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/95845453-2059-4cb4-b00a-ce55b5104871)

- Every combination of Metric & unique label is a Time Series. We have 4 time series data in the above pic.
- Instant Vector is gonna return one single sample for each time series. All are going to be a same time stamp.

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/29cda463-4388-4588-ad62-d3afd3bcdc09)

- Range vector is gonna return a range of different data points over a time-range.
- [3m] : means to get a data point over the past 3 minutes for each time series.

</br>
</br>

## 2_Selector & Matchers :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/84f01022-8d2e-4e42-be66-104348faea5e)

- Selectors :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/116429c0-090b-469a-8ab5-25c7117315ce)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f94a1655-0efc-43eb-91ea-fa0420680b9d)

- Equality Matcher :
  
![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/f41ece20-29bb-4317-a0ba-6a2da703c082)

- Negative equality Matcher :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/37160099-b2af-45e8-8b6d-c37d11a85750)

- Regex Matcher :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/708bbf4a-dcc5-4980-b0bb-be6fecfe6ee8)

- Negative Regex Matcher :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a06ee95d-2dcd-47f4-8672-bbd3a820355c)

- Multiple Selectors :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/26669dd4-c712-4462-a9e2-dc6aa0a61b8a)

- Range Vector Selectors :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/4d823e23-3d25-4c40-aef3-ddc5c3da1c11)


</br>
</br>

## 3_Modifiers :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/32b8cc49-05f6-4c54-aad8-f5bf293d0049)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/5febd48e-bd09-453b-bbd9-eb95f4851e90)

- To get the historic data :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/a3b97114-1bdf-421e-832c-de8a87d43881)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0c1b2a3d-119d-4e38-9eff-6aff4daf3d94)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/cabddf03-64d3-465e-b5eb-deff6ce43dea)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/39eead35-4858-4923-8d45-5d16ef6b61e4)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2784d678-2012-4ca1-bd91-f970176f1905)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/0ee0ada6-08c6-49be-baba-d27617ceb8ee)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/1f034944-14f0-4408-931b-beb52bd78388)

</br>
</br>

## 4_PromQL Demo :

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/8e3081e2-ed44-4e18-81cd-f9a59b1ad63e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e780f19f-dc31-471d-ad2d-7519265e7334)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/99e218c7-6493-472e-8e5f-768c5fec1bb2)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/ceb14356-f6f2-4928-af1e-fad06e797fad)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b05244e6-d506-4b91-820e-06b4ac1d447e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/661ba1de-c31f-48e9-bb60-af7231e2835e)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/e6f84c34-665f-49e1-857f-1d6491b96050)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/b5e7bed5-0d2a-41e6-8cf9-eb0964e434cd)

![image](https://github.com/its-sachink/devops_and_kodekloud_prep/assets/25415707/2d4a0055-951e-4eeb-be88-420e27e7b3c2)


</br>
</br>

## 5_Operators :




</br>
</br>

## 6_Vector Matching :

</br>
</br>

## 7_Aggregation :
