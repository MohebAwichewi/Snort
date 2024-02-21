<h1>Snort-Network-analyzer </h1>

<h2>Description</h2>
SNORT is an open-source, rule-based Network Intrusion Detection and Prevention System (NIDS/NIPS). It was developed and still maintained by Martin Roesch, open-source contributors, and the Cisco Talos team. 
The official description: "Snort is the foremost Open Source Intrusion Prevention System (IPS) in the world. Snort IPS uses a series of rules that help define malicious network activity and uses those rules to find packets that match against them and generate alerts for users."
<br />


<h2>Tools Required </h2>

- <b>Virtual Machine </b>
- <b>Snort</b>
<h2>Environments Used </h2>

- <b>debian ubuntu</b> 

<h2>Program walk-through:</h2>
<p> First, let's verify snort is installed. The following command will show you the instance version.</p>

![image](https://github.com/MohebAwichewi/Snort/assets/149394585/a7eb1674-8da0-499a-bf55-5c4bb67ff055)
<p>Before getting your hands dirty, we should ensure our configuration file is valid.

Here "-T" is used for testing configuration, and "-c" is identifying the configuration file (snort.conf).
Note that it is possible to use an additional configuration file by pointing it with "-c". </p>
![image](https://github.com/MohebAwichewi/Snort/assets/149394585/3e04f640-bb56-497e-8e99-f0e8fa077034)
<p>Once we use a configuration file, snort got much more power! The configuration file is an all-in-one management file of the snort. Rules, plugins, detection mechanisms, default actions and output settings are identified here. It is possible to have multiple configuration files for different purposes and cases but can only use one at runtime.

Note that every time you start the Snort, it will automatically show the default banner and initial information about your setup. You can prevent this by using the</p>

<p>Let's run Snort in Sniffer Mode

Like tcpdump, Snort has various flags capable of viewing various data about the packet it is ingesting.

Sniffer mode parameters are explained in the table below;

Parameter	Description
-v	Verbose. Display the TCP/IP output in the console.
-d	Display the packet data (payload).
-e	Display the link-layer (TCP/IP/UDP/ICMP) headers. 
-X	Display the full packet details in HEX.
-i	This parameter helps to define a specific network interface to listen/sniff. Once you have multiple interfaces, you can choose a specific interface to sniff. </p>
<p>Sniffing with parameter "-v"

Start the Snort instance in verbose mode (-v); sudo snort -v

Now we run the traffic-generator script as sudo and start ICMP/HTTP traffic. Once the traffic is generated, snort will start showing the  packets in verbosity mode as follows;</p>
![image](https://github.com/MohebAwichewi/Snort/assets/149394585/934e732f-607f-471a-ab58-c69706b731a1)
<p>Sniffing with parameter "-de"

Start the Snort instance in dump (-d) and link-layer header grabbing (-e) mode; snort -d -e

Now run the traffic-generator script as sudo and start ICMP/HTTP traffic. Once the traffic is generated, snort will start showing the  packets in verbosity mode as follows;</p>
![image](https://github.com/MohebAwichewi/Snort/assets/149394585/0a266391-3bed-41f2-baf9-c0748786bd4e)
<p>Sniffing with parameter "-X"

Start the Snort instance in full packet dump mode (-X); sudo snort -X

now ill the traffic-generator script as sudo and start ICMP/HTTP traffic. Once the traffic is generated, snort will start showing the  packets in verbosity mode as follows;</p>
![image](https://github.com/MohebAwichewi/Snort/assets/149394585/54aed120-5dfc-457f-bb51-92202f48951b)




