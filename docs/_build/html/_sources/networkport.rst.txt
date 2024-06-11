Connecting Zeek to an Entire Network
====================================


Imagine you’re managing a busy office network with dozens of devices, including computers, printers, and smartphones. You want to make sure you know what’s happening across your entire network and be alerted if any threats arise. Zeek is a powerful tool that can help you achieve this. 


Here's a step-by-step guide to setting up Zeek to monitor all network traffic.


1. Network Setup


 **Network Tap**
 
A network tap is a hardware device that provides a way to access data flowing across a network. It is installed between network devices, creating a copy of the data for monitoring purposes.


**How it works:**


1. Connect the tap to the network segment you want to monitor.
2. Connect the monitoring port of the tap to the Zeek server’s network interface.


**Switch Port Mirroring (SPAN Port)**


Configure a switch port as a SPAN (Switched Port Analyzer) port to mirror traffic from one or more ports or VLANs.


**How it works:**

1. Configure the SPAN port on the switch to mirror the desired traffic.
2. Connect the SPAN port to the Zeek server’s network interface.

**Inline Deployment**

Place the Zeek server inline between network segments. This setup requires two network interfaces on the Zeek server, each connecting to one segment of the network.


2. Install Zeek


**On a Unix-like system (e.g., Linux):**


1. **Install dependencies:**


   ``sudo apt-get update``
   ``sudo apt-get install cmake make gcc g++ flex bison libpcap-dev libssl-dev python3-dev swig zlib1g-dev``


2. **Download and extract Zeek:**


   `` >>>wget https://download.zeek.org/zeek-<version>.tar.gz``
      >>> tar -xzf zeek-<version>.tar.gz
      >>> cd zeek-<version>
   ``


3. **Compile and install Zeek:**

 
 ``>>>./configure
   >>> make
   >>>sudo make install
   ``

3. Configure Zeek


1. **Network Interface Configuration:**


   Edit the **node.cfg** file (usually located in ``/usr/local/zeek/etc/``) to specify the network interface that Zeek should use for monitoring. Example:
  
  
   ``cfg
   [zeek]
   type=standalone
   host=localhost
   interface=eth0
   ``

2. **Local Configuration:**
  
  
   Edit the ``local.zeek`` file to enable or customize specific scripts and logging options. This file is typically in ``/usr/local/zeek/share/zeek/site/``. Example:
 
   ``sh
   @load policy/tuning/logs-to-stdout.zeek
   ``


4. Start Zeek


To start Zeek, use the following command:
``sh
sudo zeekctl deploy
``

This command initializes Zeek and starts monitoring traffic on the specified network interface.


5. Verify Zeek is Running


Check the status of Zeek to ensure it’s running correctly:
``sh
sudo zeekctl status
``

6. Analyze Logs


Zeek logs traffic data in various log files located in the `logs` directory (usually `/usr/local/zeek/logs/`). Common logs include:
- ``conn.log`` for connection summaries.
- ``http.log`` for HTTP traffic.
- ``dns.log`` for DNS queries.


