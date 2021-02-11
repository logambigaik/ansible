# AWS SECRET MANAGER -- using this we can hide our password

![image](https://user-images.githubusercontent.com/54719289/107636983-78f13c80-6c93-11eb-80fc-11bd2f03b011.png)

      Choose Store new secert

![image](https://user-images.githubusercontent.com/54719289/107637120-a4742700-6c93-11eb-9de2-95788ca052fa.png)

## For docker_container:

      Choose other type of secret and Plain text:

![image](https://user-images.githubusercontent.com/54719289/107637231-ce2d4e00-6c93-11eb-93b5-101b19e6a0aa.png)

# Enter the password in Plain text: (Password1)

![image](https://user-images.githubusercontent.com/54719289/107637391-1482ad00-6c94-11eb-9e44-a4e8bd1c03a5.png)

#Select NEXT option


![image](https://user-images.githubusercontent.com/54719289/107641591-cffa1000-6c99-11eb-8cbe-98888aa2f353.png)


# Enter secret name and description ,click next:

![image](https://user-images.githubusercontent.com/54719289/107641877-2b2c0280-6c9a-11eb-8134-4dfdcd722e6e.png)

# Select DIsable automatic rotation and click next,

![image](https://user-images.githubusercontent.com/54719289/107642078-66c6cc80-6c9a-11eb-8715-23697411481f.png)


![image](https://user-images.githubusercontent.com/54719289/107642393-d50b8f00-6c9a-11eb-85ee-9c9408bf834d.png)


# Click store:


![image](https://user-images.githubusercontent.com/54719289/107642440-e5bc0500-6c9a-11eb-900a-14bbb7b3d183.png)


# Now key is ready  to use:


![image](https://user-images.githubusercontent.com/54719289/107642647-29167380-6c9b-11eb-9e91-81c1ec90cd53.png)


# the below info is required for further process:

![image](https://user-images.githubusercontent.com/54719289/107642875-7266c300-6c9b-11eb-8654-1a1130f6afdc.png)


# Now, encrypted ksy is DEfault Encrypted one,we can update aws/secretsmanager using action

![image](https://user-images.githubusercontent.com/54719289/107643395-16506e80-6c9c-11eb-9efc-9bb8dbcd7ea1.png)


![image](https://user-images.githubusercontent.com/54719289/107643578-56175600-6c9c-11eb-9d2d-703b2ecfbb5f.png)

![image](https://user-images.githubusercontent.com/54719289/107643628-692a2600-6c9c-11eb-82f0-d68dd58817a0.png)


# Without installing boto3 with lookup:

![image](https://user-images.githubusercontent.com/54719289/107645152-5ca6cd00-6c9e-11eb-98ba-1024e5ca96bd.png)

# Unhandled exception and expecting region:

![image](https://user-images.githubusercontent.com/54719289/107645810-3170ad80-6c9f-11eb-9060-801ac8253201.png)

# for fixing the issue ,use aws configure:

![image](https://user-images.githubusercontent.com/54719289/107646128-9e844300-6c9f-11eb-83ae-c2719d930bf7.png)


# Fixing credential issue:

    To call one service from other service, require either user permission or role permission ,so adding user in IAM.
      
  

