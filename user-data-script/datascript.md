### User data Script for `home.html `
```bash 

#!/bin/bash
yum update -y
yum install stress -y
yum install -y nginx
cat <<EOF > /usr/share/nginx/html/index.html
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
</head>
    <body><h1>Welcome to the Home Page</h1><a href="/login">Login</a></body>
</html>
EOF
systemctl enable nginx
systemctl start nginx


```
### User data script for `login.html`
```bash

#!/bin/bash
yum update -y
yum istall stress -y
yum install -y nginx
cat <<EOF > /usr/share/nginx/html/login.html
<!DOCTYPE html>
<html>
<head><title>Login</title></head>
<body>
  <h1>Login Page</h1>
  <form action="/submit" method="post">
    Username: <input type="text" name="username" required><br>
    Password: <input type="password" name="password" required><br>
    <input type="submit" value="Submit">
  </form>
</body>
</html>
EOF
systemctl enable nginx
systemctl start nginx

```
### user data script for `submit.html`
```bash

#!/bin/bash
yum update -y
yum install -y nginx
cat <<EOF > /usr/share/nginx/html/submit.html
<!DOCTYPE html>
<html>
<head><title>Submit</title></head>
<body>
  <h1>Form Submitted Successfully!</h1>
  <p>Thank you for logging in.</p>
  <a href="/home">Go back to Home</a>
</body>
</html>
EOF
systemctl enable nginx
systemctl start nginx

```