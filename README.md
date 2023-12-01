# aws-cli-import-ami-from-local-machine

- create a bucket
```git
MAINPC+abhir@MAINPC MINGW64 ~
$ aws s3api create-bucket --bucket abhiramdas99-ami-backup --region ap-south-1 --create-bucket-configuration LocationConstraint=ap-south-1
{
    "Location": "http://abhiramdas99-ami-backup.s3.amazonaws.com/"
}

```

- check the bucket is create or not
```git
MAINPC+abhir@MAINPC MINGW64 ~
$ aws s3 ls
2023-12-01 14:21:20 abhiramdas99-ami-backup
2022-11-13 21:15:27 elasticbeanstalk-ap-south-1-991987285726

```

- check the bucket is create or not
```git
MAINPC+abhir@MAINPC MINGW64 ~
$ aws s3 ls
2023-12-01 14:21:20 abhiramdas99-ami-backup
2022-11-13 21:15:27 elasticbeanstalk-ap-south-1-991987285726

```
- copy the object from local machine to that bucket
```git
MAINPC+abhir@MAINPC MINGW64 ~
$ aws s3 cp /c/my_desk/kilowott/client_projects/s*******r/ami-0e1662b79e85f27fd.bin s3://abhiramdas99-ami-backup/
Completed 340.5 MiB/1.4 GiB (9.9 MiB/s) with 1 file(s) remaining
```
- check the object is s3 bucket or not
![image](https://github.com/abhiramdas99/aws-cli-import-ami-from-local-machine/assets/62290469/5b17de68-e778-477d-a40c-1b9549ba2152)

- restire ami from s3 bucket
```git
MAINPC+abhir@MAINPC MINGW64 ~
$ aws ec2 create-restore-image-task --object-key ami-0e1662b79e85f27fd.bin --bucket abhiramdas99-ami-backup --name "webserver-ami-restore"
{
    "ImageId": "ami-0f63b8f91b803ca4d"
}

```
- check the ami create or not
![image](https://github.com/abhiramdas99/aws-cli-import-ami-from-local-machine/assets/62290469/a96bbfb2-659e-4c76-8baa-425c195a593c)

- create machine from the image
  ![image](https://github.com/abhiramdas99/aws-cli-import-ami-from-local-machine/assets/62290469/bec6d009-b9fb-4c2b-b618-d73304a26c65)

- make sure the previous data is there or not
  ![image](https://github.com/abhiramdas99/aws-cli-import-ami-from-local-machine/assets/62290469/d577d725-ee63-41bf-b501-02217525b79a)

  #Thank You!
  
 


