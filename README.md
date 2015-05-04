# ACI Diagram generator

This is a simple tool to connect to a Cisco ACI Application Policy Infrastructure Controller using the [acitoolkit](http://github.com/datacenter/acitoolkit) library, interrogate the configuration and generate logical diagrams. 

##Update
**aci-diagram is now part of the [acitoolkit](http://github.com/datacenter/acitoolkit) itself, this repository is only left for historical information. To use aci-diagram, simply install the latest acitoolkit and you'll find aci-diagram in the applications directory.**

##Installation
###Requirements
- GraphViz and the python wrapper PyGraphViz.
- [acitoolkit](http://github.com/datacenter/acitoolkit)

On MacOS, the easiest way to install the GraphViz requirements is (assuming you have HomeBrew and pip setup):

```bash
brew install graphviz
pip install pygraphviz
```

Installation instructions for the acitoolkit are [here](http://github.com/datacenter/acitoolkit)

###Downloading
If you have git installed, simply clone the repository:
	
	git clone https://github.com/cgascoig/aci-diagram.git
	
Alternatively, if you don't have git installed, [download a zip file of the repository](https://github.com/cgascoig/aci-diagram/archive/master.zip)

##Usage

The usage is simple - the login (username), password and URL arguments are required. By default the tool will include all tenants in the diagram, but you can restrict this to a subset of tenants using the `-t` argument.


```
usage: diagram.py [-h] -l LOGIN -p PASSWORD -u URL -o OUTPUT
                  [-t [TENANTS [TENANTS ...]]] [-v]

Generate logical diagrams of a running Cisco ACI Application Policy
Infrastructure Controller

optional arguments:
  -h, --help            show this help message and exit
  -l LOGIN, --login LOGIN
                        Login for authenticating to APIC
  -p PASSWORD, --password PASSWORD
                        Password for authenticating to APIC
  -u URL, --url URL     URL for connecting to APIC
  -o OUTPUT, --output OUTPUT
                        Output file for diagram - e.g. out.png, out.jpeg
  -t [TENANTS [TENANTS ...]], --tenants [TENANTS [TENANTS ...]]
                        Tenants to include when generating diagrams
  -v, --verbose         show verbose logging information
```

