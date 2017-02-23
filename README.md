View in edit mode to see more line breaks

# Executive Project Summary (NOT LONGER THAN 1 PAGE, NOT TOO SHORT)
##### Clearly identifies the context of the problem addressed by your project. Answers the question - Why is this an area of interest?
### What are you doing and why? Why is this an area of interest:
Intelligent, voice-controlled systems are a new and emerging technology now being found in many homes.  
In 2014, Amazon launched their new voice controlled assistant called Alexa.  It has been integrated into the Echo and furhter into the Echo Dot series.

Echo dots vulnerabilities for evocativeness:
Directly attached to home WiFi, Amazon Account, can do a lot of interesting things: (LIST HERE)
Skills connect device to home products = danger
Bluetooth remote that connects.
Device is brand new and hasn't been throughly investigated for vulnerabilities, potential vulnerabilitiy in many individuals' homes.

### Goals, objectives, (GOALS MUST BE BULLETED):
##### Efforts are clearly tied to addressing the identified problem. Goals are stated at a high level and are free of technical jargon or uncessary detail.
Pentesting experience
Learn how to hack devices, map devices, use cases, etc.
Plan a thourough investigation into the security of a device.
Objective is a fully-scoped pentest into Echo Dot v2.  Try and see if we can find any vulnerabilities.

### Merit
##### The benefits for pursing the project are clear and tied to addressing the identified problem(s). End user, societal, and industrial benefits are stated - if relevant.
Worthy because new firmware is hard to load (locked out of debugger) - very little research has been done.  Will be tough task to find a vulnerability

# Proposed Project Timeline
##### Specify large tasks to be completed, estimates time of completion, and arranges those tasks chronologically over the project lifespan.
## ****Gnatt chart goes here.****

Ideas for Gnatt chart:
Item | Timeframe
------------ | -------------
Milestone 2 | TBA
Milestone 3 | TBA
Construct Echo Dot usage diagrams | 1 Week
Planning | 1 Week
Acquiring Additional Hardware | 3 Weeks
Testing Network-based Vulnerabilities | 3-4 Weeks
Testing Host-based Vulnerabilities | 3-4 Weeks
Reviewing for Milestone 3 | 1 Week

# Project-oriented Risk List
##### Issues with skillsets, technology, team member availability, etc, may arise as the project goes forward.

|Risk name (value)  | Impact     | Likelihood | Description |
|-------------------|------------|------------|-------------|
|Unable to install custom firmware (27) | 3 | 9 | Firmware is locked: no known access to debugger (sdb) and no SD card slot  |
|Unable to find potential network vulnerability (18) | 3 | 6 | There may be no network-based vulnerabilities | 
|Unable to find potential vulnerability in Skills (16) ( | 2 | 8 | The custom coding skills API may have no vulnerabilites |
|Brick the Echo Dot  (20) | 10 | 2 | It is possible to brick the Echo Dot when installing firmwares.  A custom firmware, or root method, could brick the Echo Dot |

Possibles to add:
Failure to code skills
Failure to understand Android firmware and debugging
Anyone that will be unavailable for a timeframe (work, vacation, or something)

# Application Requirements
### 5 most important user stories
As a **user/role**, I want to **goal** so I can **rationale**. 
Acceptance criteria: hey
As a **user/role**, I want to **goal** so I can **rationale**. 
Acceptance criteria: hey
As a **user/role**, I want to **goal** so I can **rationale**. 
Acceptance criteria: hey
As a **user/role**, I want to **goal** so I can **rationale**. 
Acceptance criteria: hey
As a **user/role**, I want to **goal** so I can **rationale**. 
Acceptance criteria: hey

## ****Insert Use/Misuse Case Diagram Here****

# Resources/Technology Needed
##### Clearly identify the technologies, products, and languages involved in your project. Include a table that identifies which team member will investigate each needed resource. 
|Resource  | Dr. Hale needed? | Investigating Team member | Description |
|-------------------|---------|---------------------------|-------------|
|Another Echo Dot v2| Possibly | All | Having another Echo Dot v2 will allow more team members to work independently on the project  |
|Alexa Voice Remote| Possibly | All | The Bluetooth Alexa Voice Remote may be vulnerable and is worthy of investigation  |
|Android Debuggers| No | Matt | Look into SDB |
|Android Rooting| No | Matt | Look further into rooting the Echo Dot v2|
|Some way to setup airgapped testing lab| No | James | Setup a dedicated area for testing |
|Skills coding | No | Tim | Look into ways skills could be used to penetrate Echo Dot v2 |

# First Sprint Plan
https://trello.com/b/lrGlLkCc/echo-dot-project-main

# Team Members
* James Autry
* Tim Gekas
* Matthew Sutton
