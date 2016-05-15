Ansible-RHOSP
===========================

Ansible roles for installing RHOSP on existing TripleO setup.

Note: If you don't have TripleO setup, you can use ``ansible-ovb`` project deploy one on existing OpenStack cloud.

Requirments
-----------

All the packages needed for running ansible-rhosp are listed in requirements.txt

To install them, run ``pip install -r requirements.txt``

Usage
-----

Install RHOSP
^^^^^^^^^^^^^^^^^^^^

#. Edit ansible-rhosp.cfg to choose what RHOSP version to install::

       vi ansible-rhosp.cfg

       rhosp_version: 9
       repo_version: poodle

#. Run!::

       ansible-playbook -i hosts playbooks/install.yaml -e @ansible-rhosp.cfg
