# ansible_bug

ansible-playbook -i testing app.yml -e name=myenvironment -e version=1.0.0-1 -e app_name=app1 -vvv

```
(py27)bash-3.2$ pip freeze
ansible==1.9.0.1
awscli==1.7.23
bcdoc==0.13.0
boto==2.38.0
botocore==0.104.0
cmd2==0.6.7
colorama==0.3.3
dnspython==1.11.1
docutils==0.12
ecdsa==0.13
Jinja2==2.7.3
jmespath==0.6.2
libpipeline===1.2.54-3-g84b4f00
lockfile==0.10.2
lxml==3.3.5
MarkupSafe==0.23
ordereddict==1.1
paramiko==1.15.2
prettyprint==0.1.5
pyasn1==0.1.7
pycontrol==2.1
pycrypto==2.6.1
pyparsing==2.0.3
pystache==0.5.4
python-daemon==2.0.5
python-dateutil==2.4.2
PyYAML==3.11
requests==2.6.0
rsa==3.1.4
simplejson==3.5.3
six==1.9.0
suds==0.4
urllib3==1.9
(py27)bash-3.2$ ansible-playbook -i testing app.yml -e name=customer -e version=1.0.0-1 -e app_name=app1 -vvv
Traceback (most recent call last):
  File "/Users/keghol/py27/bin/ansible-playbook", line 323, in <module>
    sys.exit(main(sys.argv[1:]))
  File "/Users/keghol/py27/bin/ansible-playbook", line 156, in main
    inventory = ansible.inventory.Inventory(options.inventory, vault_password=vault_pass)
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/__init__.py", line 100, in __init__
    self.parser = InventoryDirectory(filename=host_list)
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/dir.py", line 54, in __init__
    parser = InventoryDirectory(filename=fullpath)
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/dir.py", line 58, in __init__
    parser = InventoryParser(filename=fullpath)
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/ini.py", line 43, in __init__
    self._parse()
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/ini.py", line 47, in _parse
    self._parse_base_groups()
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/ini.py", line 140, in _parse_base_groups
    host = Host(name=hn, port=port)
  File "/Users/keghol/py27/lib/python2.7/site-packages/ansible/inventory/host.py", line 32, in __init__
    self.set_variable('ansible_ssh_port', int(port))
ValueError: invalid literal for int() with base 10: 'bar'
(py27)bash-3.2$ 

```
