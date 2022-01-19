**********************
Molecule Podman Plugin
**********************

.. image:: https://badge.fury.io/py/molecule-podman.svg
   :target: https://badge.fury.io/py/molecule-podman
   :alt: PyPI Package

.. image:: https://github.com/ansible-community/molecule-podman/workflows/tox/badge.svg
   :target: https://github.com/ansible-community/molecule-podman/actions

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/python/black
   :alt: Python Black Code Style

.. image:: https://img.shields.io/badge/license-MIT-brightgreen.svg
   :target: LICENSE
   :alt: Repository License

Molecule podman Plugin is designed to allow use Podman containers for
provisioning test resources.

Please note that this driver is currently in its early stage of development.

Configuration Variables
=======================

MOLECULE_PODMAN_EXECUTABLE
--------------------------
To change the podman executable from the standard podman, export environment
variable ``MOLECULE_PODMAN_EXECUTABLE``. For instance, if you wish to run
molecule with ``podman-remote`` instead of ordinary ``podman``, the variable
can be exported as:

.. code-block:: console

   $ export MOLECULE_PODMAN_EXECUTABLE=podman-remote

MOLECULE_PODMAN_LOCAL_IMAGE_TAG_PREFIX
--------------------------------------
To change the tag prefix used for locally built images from the default of ``molecule_local``,
export environment variable ``MOLECULE_PODMAN_LOCAL_IMAGE_TAG_PREFIX``. For example, the below
will result in local images being tagged ``molecule_local_myproject/<path to upstream image>``.

This should be set when running molecule under CI/CD systems that may run more than one concurrent
molecule test as the same user using the same base/reference image
in order to avoid potential race conditions.

.. code-block:: console

   $ export MOLECULE_PODMAN_LOCAL_IMAGE_TAG_PREFIX="molecule_local_myproject"

.. _get-involved:

Implementation Notes
====================

Image Annotations
-----------------
Locally built images using the included Dockerfile are annotated with label
``com.ansible.community.generator`` set to the constant value ``molecule-podman``

Get Involved
============

* Join us in the ``#ansible-molecule`` channel on `Freenode`_.
* Join the discussion in `molecule-users Forum`_.
* Join the community working group by checking the `wiki`_.
* Want to know about releases, subscribe to `ansible-announce list`_.
* For the full list of Ansible email Lists, IRC channels see the
  `communication page`_.

.. _`Freenode`: https://freenode.net
.. _`molecule-users Forum`: https://groups.google.com/forum/#!forum/molecule-users
.. _`wiki`: https://github.com/ansible/community/wiki/Molecule
.. _`ansible-announce list`: https://groups.google.com/group/ansible-announce
.. _`communication page`: https://docs.ansible.com/ansible/latest/community/communication.html

.. _license:

License
=======

The `MIT`_ License.

.. _`MIT`: https://github.com/ansible/molecule/blob/master/LICENSE

The logo is licensed under the `Creative Commons NoDerivatives 4.0 License`_.

If you have some other use in mind, contact us.

.. _`Creative Commons NoDerivatives 4.0 License`: https://creativecommons.org/licenses/by-nd/4.0/
