# Where Am I?

Have you ever been on multiple AWS boxes at once and you don't remember what the box is for? The `whereami` command now makes it simple to figure out just where the $^@* you actually are.

## Installation

Forget fancy install scripts. Just wget the shell script and move it into the `/usr/bin` directory. But make sure your user / role has the correct permissions to run this script.

```bash
wget -q --output-document whereami https://raw.githubusercontent.com/rhyeal/whereami
/master/whereami && chmod a+x whereami && sudo mv whereami /usr/bin/whereami
```

If you get an error while running, ensure your user/role has the following IAM permission:

```
{
  "Version": "2012-10-17",
  "Statement": [
    {    
      "Effect": "Allow",
      "Action": [ "ec2:DescribeTags"],
      "Resource": ["*"]
    }
  ]
}
```
