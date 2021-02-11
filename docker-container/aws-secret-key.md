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
    
    Step1 : Add user in IAM

![image](https://user-images.githubusercontent.com/54719289/107648496-67fbf780-6ca2-11eb-8258-71e4788fdf07.png)

    Step2:              Username    : aws-secret-user 
                        Access type: Programmatic access ( If we want to allow other user then we can use AWS Management Console access)
    and click Permission
    
![image](https://user-images.githubusercontent.com/54719289/107649209-3c2d4180-6ca3-11eb-8ea1-7a46ef32ec6d.png)


     Step3:       Under Attach existingpolicy directly select secretManagerReadWrite
     
![image](https://user-images.githubusercontent.com/54719289/107649741-c675a580-6ca3-11eb-8453-974cc131684a.png)


      Step4:      Skip Add tag and its optional
      
 ![image](https://user-images.githubusercontent.com/54719289/107650333-62071600-6ca4-11eb-8fb4-47ee5436e097.png)


      Step 5: Review
      
  ![image](https://user-images.githubusercontent.com/54719289/107650416-79460380-6ca4-11eb-9a71-8b725f18c621.png)


      Step: Select Create user
      
  ![image](https://user-images.githubusercontent.com/54719289/107650522-94b10e80-6ca4-11eb-8a04-fd54b5cf407c.png)
  
              Use this credential in aws confure
                  Accee Key : AKIA34FABYBY3MUTW4VL
                  Secret Access key :  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
                  
  ![image](https://user-images.githubusercontent.com/54719289/107651435-844d6380-6ca5-11eb-875a-ea75903fc6ad.png)


# Now no issue in ansible-playbook

![image](https://user-images.githubusercontent.com/54719289/107651604-b3fc6b80-6ca5-11eb-91a3-3525f1a72d8c.png)

                  
  

                        
      
  

