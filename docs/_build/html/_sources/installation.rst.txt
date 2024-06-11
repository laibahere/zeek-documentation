Zeek Setup
=================

To run Zeek on Linux, throughout this documentation I will be using Ubuntu, a distribution of Linux, on my VMware.

Install Zeek and get it up and running by following these steps:

1. Change Privileges
^^^^^^^^^^^^^^^^^^^^

First of all, change your privileges to root:

.. code-block:: shell

   $ sudo su

2. Update and Upgrade Apt
^^^^^^^^^^^^^^^^^^^^^^^^^

Update all packages:

.. code-block:: shell

   $ apt-get update
   $ apt-get upgrade

3. Install Binary Packages
^^^^^^^^^^^^^^^^^^^^^^^^^

Install necessary packages:

.. code-block:: shell

   $ apt-get install -y --no-install-recommends g++ cmake make libpcap-dev

These packages include ``g++`` for compilation, ``cmake`` and ``make`` as build tools, and ``libpcap-dev`` to build against Zeek headers. You'll also need these dependencies for Spicy's JIT compilation.

4. Add Zeek Repository and Install
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Add Zeek repository and install:

.. code-block:: shell

   $ echo 'deb http://download.opensuse.org/repositories/security:/zeek/xUbuntu_22.04/ /' | sudo tee /etc/apt/sources.list.d/security:zeek.list
   $ curl -fsSL https://download.opensuse.org/repositories/security:zeek/xUbuntu_22.04/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/security_zeek.gpg > /dev/null
   $ sudo apt update
   $ sudo apt install zeek-6.0

5. Export Zeek Path to .bashrc
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Export Zeek path to ``.bashrc``:

.. code-block:: shell

   $ echo 'export PATH=/opt/zeek/bin:$PATH' >> ~/.bashrc
   $ source ~/.bashrc

6. Verify Zeek Installation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

To check where Zeek is located:

.. code-block:: shell

   $ which zeek

To check Zeek version:

.. code-block:: shell

   $ zeek --version

7. Check Zeek Status and Logs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Check Zeek status and logs:

.. code-block:: shell

   $ cd /downloads/zeek/bin
   $ ./zeekctl
   $ ./zeekctcl check
   $ ./zeekctcl start
   $ ./zeekctcl deploy
   $ ./zeekctcl status

8. Monitor Logs
^^^^^^^^^^^^^^

Monitor logs:

.. code-block:: shell

   $ cd /downloads/zeek/logs

Use ``tail -f`` to monitor logs. For example:

.. code-block:: shell

   $ tail -f conn.log

This command will continuously display updates in the ``conn.log`` file.

By following these steps, you should have Zeek installed, configured, and running on your system. For further details and documentation, you can refer to the official Zeek documentation available online.

