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
$ aws s3 cp /c/my_desk/kilowott/client_projects/Skillbuilder/ami-0e1662b79e85f27fd.bin s3://abhiramdas99-ami-backup/
Completed 340.5 MiB/1.4 GiB (9.9 MiB/s) with 1 file(s) remaining
```

