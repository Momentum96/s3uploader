# Reference
- BANF_SendReceive  
  https://gitlab.com/banf/banf_sendreceive/-/tree/b6a169e15f2ae2e1c851a973bb420fc843eb163b
- BANF_ClientPCSW  
  https://gitlab.com/banf/banf_sendreceive

# Requirements
- aws credential setting (for AWS S3)

# Usage
- **Works with ClientPCSW** to send data files collected from sensors to an S3 bucket when there are no changes to them.

# AWS Credentials Setting
You need to make a file named 'credentials' in '~/.aws' directory.  
in Windows, make directory at %UserProfile%.aws  
in Linux, make directory at ~/.aws  
This Package use 'default' profile in credentials file.  
So, you must set 'default' profile in credentials file.

```
# credentials file sample

[default] ; default Profile section information

aws_access_key_id = YOUR_ACCESS_KEY1

aws_secret_access_key = YOUR_SECRET_KEY
```

# Convert Python py code to an executable file

```
# use pyinstaller
pip install pyinstaller

# in root repository directory
# if you want to prevent the console window from popping up when running that Python executable, use the
pyinstaller -n "Data Collector_cli" --noconsole main.py

# If you want to pop up a console window to view error messages, use the
pyinstaller -n "Data Collector_cli" main.py

# Enter that command and the executable file will be created.
```

# Executable file usage
The command creates a build, dist folder and a Data Collector_cli.spec file, of which the actual executable is located in dist -> Data Collector_cli -> Data Collector_cli.exe.

You can't use that executable by itself, and if you want to run it in a different location, you'll need to create a shortcut to it rather than move the location of the executable itself.

An example of how this file is used can be found in [BANF_ClientPCSW](https://gitlab.com/banf/banf_clientpcsw). (bin/Debug/py_cli)