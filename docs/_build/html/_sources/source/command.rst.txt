Zeek Log Format
===============

1. **Creating a Directory for Zeek**

   To set up Zeek, create a directory for it:

   .. code-block:: shell

      $ cd /temp/
      $ mkdir zeek
      $ cd zeek

   Here, navigate to the ``/temp/`` directory, create a new directory named ``zeek``, and move into it.

2. **Defining Path and Analyzing PCAP Files with Zeek**

   Use Zeek to analyze a Packet Capture (PCAP) file:

   .. code-block:: shell

      $ /opt/zeek/bin/zeek -r ~/downloads/file.pcap

   This command parses network traffic in the PCAP file (``file.pcap``) located in the ``~/downloads/`` directory, generating various log files for analysis.

3. **Understanding Generated Log Files**

   After running Zeek, several log files are generated:

   - ``conn.log``: Contains connection records detailing source and destination IP addresses, ports, and protocols.
   - ``dns.log``: Logs DNS requests, providing insight into DNS query activity.
   - ``files.log``: Lists files transferred over the network.
   - ``http.log``: Records HTTP transactions, including requests and responses.
   - ``pe.log``: Logs portable executable (PE) files encountered in network traffic.
   - ``ssl.log`` and ``x509.log``: Provide information about TLS/SSL connections and X.509 certificates.

4. **Viewing Logs**

   Use ``less`` to view logs without line wrapping:

   .. code-block:: shell

      $ less -S conn.log

   The ``-S`` flag in ``less`` prevents line wrapping, making logs easier to read.

5. **Extracting Information from DNS Logs**

   Use ``zeek-cut`` to extract specific fields from DNS logs:

   .. code-block:: shell

      $ cat dns.log | /opt/zeek/bin/zeek-cut query

   This command extracts the ``query`` field from the ``dns.log`` file, displaying DNS queries.

6. **Counting Unique DNS Queries**

   Count unique DNS queries using a pipeline:

   .. code-block:: shell

      $ cat dns.log | /opt/zeek/bin/zeek-cut query | sort | uniq -c | sort -n

   This pipeline counts occurrences of each unique DNS query, sorting them alphabetically and numerically.

7. **Searching for Specific IDs**

   Use ``fgrep`` to search for specific IDs across all log files:

   .. code-block:: shell

      $ fgrep (id) *.log

   Replace ``(id)`` with the ID you're searching for.



8. **Analyzing HTTP Logs**

   HTTP logs (``http.log``) record HTTP transactions, including requests and responses. They provide valuable insights into web traffic, including URLs accessed, user-agents, and response codes.

9. **Analyzing SSL/TLS Logs**

   SSL/TLS logs (``ssl.log``) and X.509 certificate logs (``x509.log``) provide information about encrypted connections, including cipher suites, certificate chains, and expiration dates. They are crucial for monitoring secure communications and detecting potential security issues.

10. **Analyzing File Logs**

   File logs (``files.log``) list files transferred over the network, including their paths, sizes, and hashes. They are useful for tracking file transfers and identifying potentially malicious files.


