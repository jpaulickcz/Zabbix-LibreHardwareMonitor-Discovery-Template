**Prereq**
- **Zabbix 7 server** (I am running v7 everywhere which is what I've created this on)
- Physical Windows host with running [Zabbix agent](https://www.zabbix.com/download_agents) and running [LibreHardwareMonitor](https://github.com/LibreHardwareMonitor/LibreHardwareMonitor)

**Usage:**
- import the template into Zabbix
	- Data collection - Templates - Import & point to the .yaml from this repo
- assign it to physical Windows hosts running agent + LHM
	- Data collection - Hosts -(select host) - Templates - search for "LibreHardwareMonitor WMI"

**What it does:**
- I can't really believe no one created template like this yet or maybe I am really bad at googling but I ended up creating it myself.
- Anyway, OHM/LHM by default makes all of its values accessible via WMI
- Zabbix can do WMI queries on the host through the agent, so my goal was to create as lightweight ingest of this data as possible - no scripts on hosts, no pulling LHM's json via its webserver etc.
- This template pulls everything that is type "Temperature" and creates item for everything it finds - just disable afterwards the items you don't want

**Todo list**
- figure out how to make LHM run as a service 
- test it on as many physical windows hosts as possible (I don't have many)
- add fan speeds for monitoring for fan failures, possibly other monitoring worthy items
- create prototypes for alerts (not sure how yet)... mostly I want to have historical data to see in summer if maybe some unstability is due to overheating/high temps
