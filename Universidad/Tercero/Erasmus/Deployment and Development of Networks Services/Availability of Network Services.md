#Theory/Networks 
# Introduction
A system is said to be _available_ if it is running and usable. There are many ways to check the availability of a system,  such as percentages, number of nines(Counting the number of nines in a row from left to right). There are other common measurements such as:
- MTTF(Mean Time To Failure): It should not be longer than the system life expectancy
- MTTR(Meant Time To Repair)
- MTBF(Meant TIme Between Failures)
- Error rate
The error rate has a graphic that should ideally look like this:
![[Pasted image 20230101181545.png]]

# Causes of System Failures
There are technical and organizational failures
- Technical
	- Breakage of hardware
	- Loss of Power
	- Software Malfunction
	- Unavailability of software or backups
- Organizational
	- Bad Implementation
	- Improper or non existing bacups
	- Improper maintenance
	- NNo crisis resolution plans
	- Loss of key personel
	- Cyber attacks
# Architectural patterns for high availability
- Replication of systems
![[Pasted image 20230101183024.png]]

- Server Farm
![[Pasted image 20230101183034.png]]
