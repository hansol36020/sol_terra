# sol_terra

# seoul Zone ssh
```
'ec2-52-79-235-39.ap-northeast-2.compute.amazonaws.com,52.79.235.39' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.4 LTS (GNU/Linux 4.15.0-1065-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue May 12 09:17:02 UTC 2020

  System load:  0.08              Processes:           89
  Usage of /:   16.0% of 7.69GB   Users logged in:     0
  Memory usage: 16%               IP address for eth0: 172.31.38.164
  Swap usage:   0%


31 packages can be updated.
16 updates are security updates.

```
###curl Nginx public ip
```
on complete after 2m3s [id=i-0ffc59d817cf2f195]

Apply complete! Resources: 2 added, 0 changed, 0 destroyed.
            "public_ip": "52.79.235.39",

```
```
curl 52.79.235.39:80
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
   body {
       width: 35em;
       margin: 0 auto;
       font-family: Tahoma, Verdana, Arial, sans-serif;
   }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

```


## seoul, instance 1, create
```
ta

terraform destroy -auto-approve
terraform init
terraform apply -auto-approve
cat terraform.tfstate|grep public_ip|grep -v associate


Destroy complete! Resources: 0 destroyed.

Initializing the backend...

Initializing provider plugins...

The following providers do not have any version constraints in configuration,
so the latest version was installed.

To prevent automatic upgrades to new major versions that may contain breaking
changes, it is recommended to add version = "..." constraints to the
corresponding provider blocks in configuration, with the constraint strings
suggested below.

* provider.aws: version = "~> 2.60"

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
aws_key_pair.mykey: Creating...
aws_key_pair.mykey: Creation complete after 0s [id=mykey]
aws_instance.example: Creating...
aws_instance.example: Still creating... [10s elapsed]
aws_instance.example: Still creating... [20s elapsed]
aws_instance.example: Provisioning with 'file'...
aws_instance.example: Still creating... [30s elapsed]
aws_instance.example: Still creating... [40s elapsed]
aws_instance.example: Still creating... [50s elapsed]
aws_instance.example: Still creating... [1m0s elapsed]
aws_instance.example: Still creating... [1m10s elapsed]
aws_instance.example: Still creating... [1m20s elapsed]
aws_instance.example: Still creating... [1m30s elapsed]
aws_instance.example: Still creating... [1m40s elapsed]
aws_instance.example: Provisioning with 'remote-exec'...
aws_instance.example (remote-exec): Connecting to remote host via SSH...
aws_instance.example (remote-exec):   Host: 52.79.235.39
aws_instance.example (remote-exec):   User: ubuntu
aws_instance.example (remote-exec):   Password: false
aws_instance.example (remote-exec):   Private key: true
aws_instance.example (remote-exec):   Certificate: false
aws_instance.example (remote-exec):   SSH Agent: false
aws_instance.example (remote-exec):   Checking Host Key: false
aws_instance.example (remote-exec): Connected!
aws_instance.example (remote-exec): 0% [Working]
aws_instance.example (remote-exec): Hit:1 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic InRelease
aws_instance.example (remote-exec): 0% [Connecting to security.ubuntu.com (
aws_instance.example (remote-exec): Get:2 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
aws_instance.example (remote-exec): Get:3 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
aws_instance.example (remote-exec): 0% [3 InRelease 64.9 kB/74.6 kB 87%] [C
aws_instance.example (remote-exec): 0% [Connecting to security.ubuntu.com (
aws_instance.example (remote-exec): 0% [1 InRelease gpgv 242 kB] [Connectin
aws_instance.example (remote-exec): 0% [Connecting to security.ubuntu.com (
aws_instance.example (remote-exec): 0% [2 InRelease gpgv 88.7 kB] [Waiting
aws_instance.example (remote-exec): Get:4 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic/universe amd64 Packages [8570 kB]
aws_instance.example (remote-exec): 0% [2 InRelease gpgv 88.7 kB] [4 Packag
aws_instance.example (remote-exec): 0% [2 InRelease gpgv 88.7 kB] [Waiting
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [2 InRelease
aws_instance.example (remote-exec): Get:5 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic/universe Translation-en [4941 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [2 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [5 Translatio
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:6 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:7 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse amd64 Packages [151 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:8 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic/multiverse Translation-en [108 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:9 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [932 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:10 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/main Translation-en [318 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:11 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [50.1 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:12 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/restricted Translation-en [12.6 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:13 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [1068 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:14 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/universe Translation-en [332 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:15 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [15.5 kB]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): Get:16 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-updates/multiverse Translation-en [6352 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [3 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [6 InRelease
aws_instance.example (remote-exec): Get:17 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main amd64 Packages [7516 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [6 InRelease
aws_instance.example (remote-exec): Get:18 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/main Translation-en [4764 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [Waiting for
aws_instance.example (remote-exec): Get:19 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [7484 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [Waiting for
aws_instance.example (remote-exec): Get:20 http://ap-northeast-2.ec2.archive.ubuntu.com/ubuntu bionic-backports/universe Translation-en [4436 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [6 InRelease
aws_instance.example (remote-exec): 0% [4 Packages store 0 B]
aws_instance.example (remote-exec): 0% [4 Packages store 0 B] [6 InRelease
aws_instance.example (remote-exec): 86% [4 Packages store 0 B]
aws_instance.example (remote-exec): Get:21 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [707 kB]
aws_instance.example (remote-exec): 86% [4 Packages store 0 B] [21 Packages
aws_instance.example (remote-exec): 87% [21 Packages 101 kB/707 kB 14%]
aws_instance.example (remote-exec): 87% [5 Translation-en store 0 B] [21 Pa

  ]
}

```
