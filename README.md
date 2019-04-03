# aws_iam_policy
IAM in AWS provides several roles to help customers protect their project and resources. <br/>
There are users, groups, roles, and permissions.
<br/>
<br/>
In general, for users, you can create multiple users and assign passwords for them. After that, 
if you want to create one user using AWS CLI, you can 
```
    aws iam create-user --user-name ...
```
but, you cannot do anything just create a single user. You need to associate the user with group attached with some specific policy.
<br/>
<br/>
for groups, if you want to create one user using AWS CLI, you can
```
    aws iam create-group --group-name ...
    e.g.   
        aws iam create-policy --policy-name my-policy --policy-document file:///tmp/aws_test_policy.json
```
if you want to attach some policy to this group, you can
```
    aws iam put-group-policy --group-name ... --policy-name ... --policy-document ...
    e.g.
        aws iam put-group-policy --group-name group_temp --policy-name my-policy --policy-document file:///tmp/aws_test_policy.json
```
<br/>
<br/>
for roles, to do ...


<br/>
<br/>
for policy, you can create the policy based on the json file. <br/>
There are PARCE principle. <br/>
Principal: normally omitted, will get the principle from outside(like user, group, roles) <br/>
Action: <br/>
Resource:  <br/>
Condition: can be omitted, which means no additional condition <br/>
Effect:  <br/>

````````
for example
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::corp-fs-web-bucket/*"
        }
    ]
}
````````

refer:
https://www.imooc.com/article/47391 <br/>
https://blog.csdn.net/whatnamecaniuse/article/details/78396384

Note, aws_test_policy.json is used for aws cli command and aws_iam_policy.json is used for aws iam management console
