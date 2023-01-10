A security level is the recognition of an achievement along the security journey learning platform

### Defining Security
- Since we live in a connected world with software being everywhere; we must have a barrier to protect our most coveted assets
- People (build the product) => Process (the standard way to help apply the security) and Tools (what helps us)

Attackers (people or places)
- one who exploits vulnerabilities 

Application and Software security
- App - we prevent the vulnerabilities and Software - we build our software in a way to 

Attack surface - the interfaces an attacker could use to attempt to compromise the security

Developers 
- Through secure design and implementation to prevent problems of exploitation as they build software


### Key Security Concepts:
- The CIA triad: Confidentiality (company information should not be exposed for access to those anauthorised), Integrity (information can be trusted by anyone authorized), Availability (company info should be available for access to anyone authorized) are the building blocks of application security
- A vulnerability: a weakness in the system that might be exploited. 
- An exploit is a weaponized program that takes advantage of a software vulnerability or security flaw. It is written either by security researchers as a proof-of-concept threat or by malicious actors for use in their operations.
- An attack is an attempt to exploit a weakness
- Stages of a security framework: identify, protect, detect, respond, recover
- Red team is offensive, blue team is defensive and the purple team is a red team working with blue team together

Attacks
- The systems we build are going to be attacked, so we need to understand how to combat these.
	Attackers have a process with a goal in mind:
		- Defining a target and objective -> Research is made on it (employees, website, etc) -> Initial intrusion (phishing emails, zero-day attacks, etc) -> persistence -> Lateral movement (getting into more systems which might host sensitive information) -> Data gathering (the optimal desire to get the information using Exfiltrate copying the data) -> Cover tracks (log files)
	
	Four common attacks
	- Buffer overflow: an attacker may send too much information to a system to go over the maximum memory allocated to a specific software; where there's no checks being done, this will be an easy attack
		- Local buffer-overflow: access to the local system; product or server to execute code as an exploit
		- Remote: the attacker is sitting on the other side of the internet and launches an exploit that takes advantage of a user's machine over the internet
		- The attacker is trying to get priviledge access which makes the  attacker have all permissions

	- Web based attacks:
		- SQL injection, Cross site scripting, Cross site request forgery (CSRF)
		- Denial of service (as an attacker, the aim is to get your system offline, where no custormer or anyone else may access it)
			- Single packet: less traffic, may be sent every minute, may cause the system to reboot and no one have access to it
			- Distribute Denial of Service (DDOS): a lot more complicated since it aims to send as much traffic as it can to a system to overwhelm it with requests
				- Intermediary systems called handlers may be used to create other attack systems called zombies which then flood the site with requests
		- Social engineering; an attacker may try to learn about the future road map of products. A human based attack; tricking the victim to give some information using a story that is not true
		
	- Negative Results: 
		- Product/system/application may be compromised, no longer available for access
		- Data breach; customer information may be stolen and leaked off in the dark market
		- Malware (mallicious software run on the machine)/ransomware infection (scrambled files in search of a ransom to give back control)

Attackers
---
- Why do we care about them? If we know something about their motivation it helps us shut the possible doors they could exploit

	Types of Attackers
	* Organized crime: professional criminals who use the internet for unlawful activities (corporate espionage: practice of spying)*
	* State affiliated: an individual/group with a global government that attacks to disrupt or compromise governments, orgs or other individuals
	* Evil sys admin: in insider with elevated and legitimate access and knowledge of a computer sys, used for illegitimate gain
	* Hacktivist: someone or loosely organized group whose activity is aimed at promoting a social or political cause
	* Insiders: Empoyees, contractors or partners that carry out criminal activities using legitimate access

* Hats concepts are used to identify who the bad person or good (taken from cowboy movies) and their motivation
	* White hat: one who knows how to break into a system and then uses their knowledge to help the company or individual to protect themselves from these vulnerabilities
	* Motivation: financial gain, espianoge (theft of interna/intellectual property: downloading source code, etc), fun (out of enjoyment), grudge due to treatment in the company

Reveue of Cybercrime : $1.5T

Depths of the internet: 
	* Surface net: sites accessible via web browser
	* Deep net: blocks web browsers from accessing them
	* Dark net: you must have special software or browser to get into it (various market places, illicit styles, because there isn't ways to track it)
	* 
	Data has a value and when it is in a breach

APT - Advance Persistent Threat
	- A cyberattack: 
		- a) executed by criminals or nation-states with the intent to steal data or surveil systems over an extended time period 
		- b) with a specific target and goal 
		- c) which has spent time and resources to identify which vulnerabilities they can expoit to gain access, and designs an attack that will likely remain undetected for a long time
	- Common traits:
		- Funded by global governments (specific states)
		- Target specific economical sectors
		- Utilize bublic and non public malware families
		- Specific attack vectors (they follow certain patterns that makes it easy to identify them and track down)
- We need to help to defend against all these threats to our contries and organizatio
- 
### Data Breaches
- This is an event where confidential data has potentially been viewed, stolen or used by an individual unauthorized to do so
- We care because we don't want to see our company being on a page where it has been exploited.

	Business impacts
	- Data loss: information collected over a period of time can be lost in just one quick event
	- Breach clean up costs; to figure out what went wrong and doing mitigation
	- Revenue impact; customers closing and removing their investments and trust
	- Reputational impact
- Elements of Data breaches
	- Attacker researches target

Lessons learned for data breaches
- Patching is key; patch management is hard to do in an enterprise
- External web app testing is a must for all public facing apps
- Own failures ASAP

PDL and OxyData: companies that scrape data from all over networks bringing it to one server
	- Elastic search data
	- What went wrong: this server was publicly available and accessible to all via the browser.
	- Lesson: don't attach unprotected data to public



#### Security Business Case
- Since our customers trust us with their data, they expect us to protect it or use it in an uncompromising way 
	- Customer security verification: the use of the product by customers
	- Business Secure Development Lifecycle
	- Expectation of Foundational Security
- 81% of customers would stop interacting with a business online after a data breach is reported with them
- 55% of customers will stop being part of a company if their data is shared with other parties outside of their consent

##### shift left - shift right
	- Security needs to be embedded into the development process 

Starting with secure security process decreasing the costs of fixing bugs