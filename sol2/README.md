# sol2

##instance 4, Nginx
```
aws_instance.example[3]: Creation complete after 1m16s [id=i-05c6dd14d1c05e7a7]
aws_instance.example[1]: Creation complete after 1m19s [id=i-02657862336c1a601]

Apply complete! Resources: 5 added, 0 changed, 0 destroyed.
            "public_ip": "3.250.80.31",
            "public_ip": "54.154.244.106",
            "public_ip": "54.77.12.95",
            "public_ip": "52.215.73.239",
```
####nginx curl
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
ubuntu@u1:~$ curl 52.215.73.239:80
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

```
