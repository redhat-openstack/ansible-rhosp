Ansible-RHOSP
=============

Ansible roles for installing RHOSP 11 on existing TripleO setup.

To install different version, checkout one of the existing branches:

To install RHOSP 10::
    git checkout stable/10

To install RHOSP 9::
    git checkout stable/9

To install RHOSP 8::
    git checkout stable/8

To install RHOSP 7::
    git checkout stable/7


Note: If you don't have TripleO setup, you can use ``ansible-ovb`` project to deploy such setup on existing OpenStack cloud.

Requirments
-----------

1. Packages listed in ``requirements.txt``. Install them by using ``pip install -r requirements.txt``.

2. hosts file with the undercloud entry::

    [undercloud]
    <undercloud_IP_or_name>

Make sure you have password-less connection to the undercloud host.

Usage
-----

Install RHOSP 11
^^^^^^^^^^^^^^^^
#. Specify the number of nodes you would like to install in ansible-rhosp.yml::

    vi ansible-rhosp.yml

    controller_nodes: 1
    compute_nodes: 1
    ceph_nodes: 0
    block_storage_nodes: 0
    swift_nodes: 0

#. Run the following command::

    ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.yml
