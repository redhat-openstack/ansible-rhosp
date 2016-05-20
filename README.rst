Ansible-RHOSP
===========================

Ansible roles for installing RHOSP on existing TripleO setup.

Note: If you don't have TripleO setup, you can use ``ansible-ovb`` project deploy one on existing OpenStack cloud.

Requirments
-----------

#. All the packages needed for running ansible-rhosp are listed in requirements.txt

To install them, run ``pip install -r requirements.txt``

#. hosts file with the following entry:

```
[undercloud]
<undercloud_IP_or_name>
```

Usage
-----

Install RHOSP
^^^^^^^^^^^^^^^^^^^^

#. Run the following command:

       ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.cfg
