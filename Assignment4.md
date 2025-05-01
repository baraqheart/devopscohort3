## PART 1: SETUP

### Launch Instances using Aws cl
- prerequisite: understanding IAM users and role 

### Step1: Create IAM for access
- Create an IAM user for only pragmatic access
- assignment 'administrative' permission
- copy Aws acess key ID and secret key somewhere safe

### Step2: Install AWs cli
- visit aws website to get the (latest link)[https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html] or

- install it (here)[]
```h
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

./aws/install -i /usr/local/aws-cli -b /usr/local/bin

``` 

### Step3: Configure access

- enter `aws configure` and press enter on the terminal
- enter both key ID and secret key
- enter your preffered region or press enter to maintain default
- choose you output style, json or yaml.
- now you will be able to interact with your aws account
without using the console

- use `aws --version` to confirm installation


### PART 2: DEPLOYMMENT

1. Create vpc and get the id

`aws ec2 create-vpc --cidr-block 10.0.0.0/16`

`aws ec2 describe-vpcs`

2. Create a subnet

`aws ec2 create-subnet --vpc-id <vpc_id> --cidr-block 10.0.1.0/24 --availability-zone us-east-1a`


3. create keypair

```bash
aws ec2 create-key-pair --key-name MyKeyPair --query 'KeyMaterial' --output text > MyKeyPair.pem
chmod 400 MyKeyPair.pem
```
4. Get Security group id
- get an id from the existing security groups available

5. create instance

```bash
aws ec2 run-instances --image-id ami-0abcdef1234567890 --instance-type t2.micro --key-name MyKeyPair --subnet-id <subnet_id> --security-group-ids <sg_if>
```
- login to instance and setup apache2

6. create an s3 bucket

`aws s3 mb s3://your-bucket-name --region your-region`

7. upload website zip file to s3 bucket

`aws s3 cp your-own-directory s3://your-bucket-name`

8. copy file to your instance and unzip it

`aws s3 cp s3://my-bucket/website.zip /home/ec2-user/`

### Part 3: Cleanup
- delete or terminate instance

`aws ec2 terminate-instances --instance-id`

- delete keypair
`aws ec2 delete-key-pair --key-name MyKeyPair`

- delete subnet
`aws ec2 delete-subnet --subnet-id <subnetname>`

- delete vpc
`aws ec2 delete-vpc --vpc-id <vpc-id>`

- detele s3 bucket and content also
