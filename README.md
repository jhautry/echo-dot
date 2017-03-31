# Executive Project Summary
### Summary and Merit of Project
Intelligent, voice-controlled systems are a new and emerging technology now being found in many homes.  
In 2014, Amazon launched their new voice controlled assistant called Alexa.  It has been integrated into the Amazon Echo and into the Amazon Echo Dot series.  These are devices which sit in a user's home, constantly listening for the user to make a request that Alexa could fulfill.  Examples of requests that can be fulfilled are playing music, giving information on the weather, or controlling another Internet of Things (IoT) device in the user's home.

Our primary objective is to execute a full-scope pentest into the Amazon Echo Dot (2nd Generation).  Specifically, this refers to compromising the security of the device itself - not the security of Alexa, whose implementation is stored on official Amazon servers.  However, there are devices that are made to interface with the Echo Dot (namely, the Alexa Voice Remote) that we will also be inspecting to see if they can be used to compromise the Echo Dot.

Voice-controlled AI devices such as the Echo Dot are a newly emerging technology, and there is still a lot of research and testing that needs to be done before these IoT devices can be said to have been properly vetted for widespread use.  In pentesting the Echo Dot, we hope to accomplish one of two ends: either improve the assurance that these devices are secure enough for widespread use, or improve the security of the device so that it can eventually be suitable for widespread use.

### Goals and objectives
* Gain valuable experience pentesting as a team
* Plan a thorough investigation into the security of the Echo Dot
* Test the following strategies:
  * Intercept the Echo Dot's Wi-Fi communications and execute Man-in-the-Middle based attacks
  * Spoof an Alexa Voice Remote signal
  * Attempt to be the first known group to root an Echo Dot v2 
  * If rooting is successful, attempt to develop a proof-of-concept firmware exploit
  * Find a vulnerability that could lead to compromise of the Echo Dot through the Skills API
  * Develop secure usage practices by finding the threshold decibel levels required to converse with Alexa
* Provide a technical writeup concerning the results of our investigation into the Echo Dot, both for the benefit of Amazon so that they may patch any vulnerabilities we find, and for the rest of the security community, so that they may build off our work

# Proposed Project Timeline
Timeline last updated: 3/9/2017

### Gantt Chart
![Project Gantt Chart](https://raw.githubusercontent.com/jhautry/echo-dot/master/Echo%20Dot%20Project%20Timeline%203-9%20v2.png)

### Tabular Project Timeline
|Item | Start | End | Duration
|------------ | -------------|-------------|-------------|
|Planning | 3/2 | 3/9 | 1 Week|
|Continued Research | 3/2 | 3/23 | 3 Weeks|
|Acquire Additional Hardware | 3/2 | 3/23 | 3 Weeks|
| **M2** Design Architectural Diagrams | 3/2 | 3/30 | 4 Weeks|
| **M2** Design Activity Diagrams | 3/9 | 3/30 | 3 Weeks|
|*Pentest Network Vulnerabilities | 3/9 | 4/13 | 5 Weeks|
|*Pentest Skills API | 3/9 | 4/13 | 5 Weeks|
|*Pentest Firmware Vulnerabilities | 3/23 | 4/13 | 3 Weeks|
|*Pentest Alexa Remote | 3/23 | 4/13 | 3 Weeks|
| **M2** Develop User Story Realizations | 3/23 | 4/3 | 11 Days|
| **M2** Develop Milestone 3 Kanban Board | 3/23 | 4/3 | 11 Days|
| **M2** Create Presentation Slides | 3/23 | 4/6 | 2 Weeks|
|**Milestone 2 Due** | 4/3 | 4/3 | **DUE** |
|**Milestone 2 Presentations** | 4/6 | 4/6 | **DUE** |
|Write Final Report | 4/6 | 4/27 | 3 Weeks|
|Milestone 3 Due | TBA |  |  |
|Final Presentations | TBA |  |  |

# Project-oriented Risk List
|Risk name (value)  | Impact     | Likelihood | Description |
|-------------------|------------|------------|-------------|
|Unable to install custom firmware (27) | 3 | 9 | Firmware is locked: no known access to debugger (sdb) and no SD card slot  |
|Lack of team availability (24) | 6 | 4 | There is a possibility that there will be scheduling issues down the road which could lead to a loss of productivity |
|Brick the Echo Dot  (20) | 10 | 2 | A custom firmware install, or root method, could brick the Echo Dot |
|Unable to find potential network vulnerability (18) | 3 | 6 | There may be no network-based vulnerabilities | 
|Unable to find potential vulnerability in Skills (16) | 2 | 8 | The custom coding skills API may have no vulnerabilities |

# User Stories
### 1) As an *end user*, the main action I will be conducting is *giving verbal requests to Alexa* so I can *have her automate tasks for me like a personal assistant*.

Acceptance Criteria:
* Obtain a fundamental understanding of the hardware and software routines used by the Echo Dot and Alexa.
* Pentest the default Echo Dot features for vulnerabilities.

---

### 2) As an *end user*, I want to *be confident that my Echo Dot is secure* so I can *trust it to administer the security of my home* and *maintain confidentiality of my personal information*.

Acceptance Criteria:
* Pentest the default Echo Dot features for vulnerabilities.
* Pentest the Echo Dot's IoT capabilities.
* Identify and outline any user credentials stored on the Echo Dot.
* Determine if identified user credentials are stored securely (i.e. encrypted).
* Determine if confidential network traffic to and from the Echo Dot is transmitted securely  (i.e. encrypted).
* Determine if there is an unsecure, remote method of communication to the Echo Dot that can be abused by malicious outsiders.
* Identify safe placement practices for Echo Dots by finding the threshold decibel levels required to converse with Alexa.

---

### 3) As an *end user*, I want to *download and install an Alexa Skill* to my Echo Dot so I can *add new features over time*.

Acceptance Criteria:
* Pentest the Alexa Skill download system.
* Research if any malicious Alexa Skills have been developed successfully.
* Research programming capabilities that are projected to be added to future versions of the Skills API and identify their potential vulnerabilities.
  
Activity Diagram:
![Third User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US3%20Activity%20Diagram%20v1.png)

---

### 4) As a *developer*, I want to *be able to create an Alexa Skill* that users will find useful so they can *improve their Echo Dot functionality*.

Acceptance Criteria:
* Determine if the latest version of the Alexa Skills API can be used to program a malicious Skill.
* If there exists a potential Skills API vulnerability, attempt to provide a proof-of-concept for the exploit.
* Research and determine if any malicious Alexa Skills have been developed successfully.
* Research programming capabilities that could be added to future versions of the Skills API and identify their potential vulnerabilities.

---

### 5) As an *Amazon employee*, I want to *ensure the Echo Dot has no critical firmware update vulnerabilities* so that *malicious users cannot remotely flash their own firmware onto unauthorized Echo Dots*.

Acceptance Criteria:
* Pentest the firmware update system.
* Determine if network-based replay attacks can be used to spoof an unauthorized firmware update.
* Attempt to root the Echo Dot by unlocking the bootloader 
  
---


# Use/Misuse Case Diagram

![Use/Misuse Case Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/Echo%20Dot%20Use%2BMisuse%20Case%20Diagram%20v2.png)

# Resources/Technology Needed
|Resource  | Dr. Hale needed? | Investigating Team member | Description |
|-------------------|---------|---------------------------|-------------|
|Another Echo Dot v2| Yes | All | Having another Echo Dot v2 will allow more team members to work independently on the project  |
|Alexa Voice Remote| Yes | All | The Bluetooth Alexa Voice Remote may be vulnerable and is worthy of investigation  |
|WiFi Pineapple| Yes | James | For testing man-in-the-middle attack possibilities |
|Android Debuggers| No | Matt | Look into Android debuggers |
|Android Rooting| No | Matt | Look further into rooting the Echo Dot v2|
|Some way to setup air gapped testing lab| No | James | Setup a dedicated area for testing |
|Skills coding | No | Tim | Look into ways skills could be used to penetrate Echo Dot v2 |

# First Sprint Plan
https://trello.com/b/lrGlLkCc/echo-dot-project-main

# Team Members
* James Autry - jhautry
* Tim Gekas - tgekas
* Matthew Sutton - nfiniteecho
