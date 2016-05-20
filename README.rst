Ansible-RHOSP
===========================

Ansible roles for installing RHOSP 8 on existing TripleO setup.

Note: If you don't have TripleO setup, you can use ``ansible-ovb`` project deploy one on existing OpenStack cloud.

Requirments
-----------

1. Packages listed in ``requirements.txt``. Install them by using ``pip install -r requirements.txt``.

2. hosts file with the following entry::

    [undercloud]
    <undercloud_IP_or_name>

Usage
-----

Install RHOSP 8
^^^^^^^^^^^^^^^^^^^^

#. Run the following command::

    ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.cfg
