Prereq
- Zabbix 7
- Windows host with running Zabbix agent and running LHM

What it does
- I can't really believe no one created template like this yet or maybe I am really bad at googling but I ended up creating it myself.
- Anyway, OHM/LHM by default makes all of its values accessible via WMI
- Zabbix can poll WMI queries on the agent, so my goal was to create as lightweigt ingest of this data as possible
- This template pulls everything that is type "Temperature" and creates item for everything it finds

That's it for now


Todo list
- test it on as many physical windows hosts as possible (I don't have many)
- add fan speeds for monitoring for fan failures, possibly other monitoring worthy items
- create protypes for alerts (not sure how yet)... mostly I want to have historical date to see in summer if maybe some unstability is due to overheating
