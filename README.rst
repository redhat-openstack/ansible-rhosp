Ansible-RHOSP
=============

Ansible roles for installing RHOSP 9 on existing TripleO setup.

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

Install RHOSP 8
^^^^^^^^^^^^^^^
#. Specify the number of nodes you would like to install in ansible-rhosp.cfg::

    vi ansible-rhosp.cfg

    controller_nodes: 1
    compute_nodes: 1
    ceph_nodes: 0
    block_storage_nodes: 0
    swift_nodes: 0

#. Run the following command::

    ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.cfg
