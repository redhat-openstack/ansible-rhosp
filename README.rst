Ansible-RHOSP
===========================

Ansible roles for installing RHOSP on existing TripleO setup.

Note: If you don't have TripleO setup, you can use ``ansible-ovb`` project deploy one on existing OpenStack cloud.

This will install **RHOSP 9**.

To install older version, checkout one of the following branches:

RHOSP 7 -> ``git checkout stable/7``

RHOSP 8 -> ``git checkout stable/8``

Requirments
-----------

All the packages needed for running ansible-rhosp are listed in requirements.txt

To install them, run ``pip install -r requirements.txt``.

In addition, you should have hosts file that includes entry for undercloud host::

       [undercloud]
       <undercloud_IP_or_hostname>

Usage
-----

Install RHOSP
^^^^^^^^^^^^^^^^^^^^

#. Edit ansible-rhosp.cfg to set the number of nodes you would like to install::

       vi ansible-rhosp.cfg

       controller_nodes: 1
       compute_nodes: 1
       ceph_nodes: 0
       block_storage_nodes: 0
       swift_nodes: 0

#. Run!::

       ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.cfg
