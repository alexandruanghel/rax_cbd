rax_cbd 
---------

**create / delete / resize a Rackspace Cloud Big Data cluster**

This is an Ansible module that allows to create, resize and delete a Rackspace Cloud Big Data cluster.
It can wait for the cluster to be built (configurable) and offers a variety of configurable options.

### Prerequisites
- `python-lavaclient` module for Cloud Big Data has to be installed: http://docs.rackspace.com/cbd/api/v1.0/cbd-getting-started/content/installing_Client.html

- `pyrax` Python module: https://github.com/rackspace/pyrax

  Also recommended is to run `pip install oslo.config netifaces`.

- It uses the standard pyrax credentials file that looks like:
  ````
  [rackspace_cloud]
  username = my_username
  api_key = 01234567890abcdef
  ````
  
  This file will be referenced in `group_vars/all` (the `rax_credentials_file` variable).

  By default, the file is expected to be: `~/.raxpub`

### How to use it

Being a custom Ansible module, it can be used in a couple of different ways:

* put the file in a library folder under the structure of your cookbook (like in this example playbook)
* have ANSIBLE_LIBRARY environment variable to point to the folder where the module resides

### Example run:

- Customize the cluster settings via the `group_vars/all` file.

- Run:
  ````
  ansible-playbook -i inventory cbd.yml
  ````
