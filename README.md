# Executive Project Summary
### Summary and Merit of Project
Intelligent, voice-controlled systems are a new and emerging technology now being found in many homes.  
In 2014, Amazon launched their new voice controlled assistant called Alexa.  It has been integrated into the Amazon Echo and into the Amazon Echo Dot series.  These are devices which sit in a user's home, constantly listening for the user to make a request that Alexa could fulfill.  Examples of requests that can be fulfilled are playing music, giving information on the weather, or controlling another Internet-Of-Things device in the user's home.

Our primary objective is to execute a full-scope pentest into the Amazon Echo Dot (2nd Generation).  Specifically, this refers to compromizing the security of the device itself - not the security of Alexa, whose implementation is stored on official Amazon servers.  However, there are devices that are made to interface with the Echo Dot (namely, the Alexa Voice Remote) that we will also be inspecting to see if they can be used to compromize the Echo Dot.

Voice-controlled AI devices such as the Echo Dot are a newly emerging technology, and there is still a lot of research and testing that needs to be done before these Internet-of-Things devices can be said to have been properly vetted for widespread use.  In pentesting the Echo Dot, we hope to accomplish one of two ends: either improve the assurance that these devices are secure enough for widespread use, or improve the security of the device so that it can eventually be suitable for widespread use.

### Goals and objectives
* Gain valuable experience with pentesting as a team
* Plan a thourough investigation into the security of the Echo Dot
* Test the following general compromization strategies:
  * Intercept Echo Dot connection to WiFi in order to execute Man-in-the-Middle based attacks
  * Overwrite firmware with potentially malicous version
  * Spoof signal from Alexa Voice Remote
  * Find vulnerability that could lead to compromization of the Echo Dot through the Skill API
* Provide a comprehensive writeup concerning the results of our investigation into the Echo Dot, both for the benefit of Amazon so that they may patch any vulnerabilities we find, and for the rest of the security community, so that they may build off our work

# Proposed Project Timeline
![Project Gantt Chart](/Echo Dot Project Timeline v2.png)

|Item | Start | End | Duration
|------------ | -------------|-------------|-------------|
|Planning | 3/2 | 3/9 | 1 Week|
|Continued Research | 3/2 | 3/23 | 3 Weeks|
|Acquire Additional Hardware | 3/2 | 3/16 | 2 Weeks|
|Diagram Echo Dot Hardware | 3/2 | 3/16 |  1 Week|
|Pentest Network Vulnerabilities | 3/9 | 4/13 | 5 Weeks|
|Pentest Firmware Vulnerabilities | 3/9 | 4/13 | 5 Weeks|
|Find Vulnerability in Skills API | 3/9 | 4/13 | 5 Weeks|
|Find Vulnerability in Alexa Remote | 3/16 | 4/13 | 4 Weeks|
|Write Report | 4/6 | 4/27 | 3 Weeks|
|Create Presentation Slides | 4/6 | 4/20 | 3 Weeks|
|Milestone 2 | TBA |  |  |
|Milestone 3 | TBA |  |  |
|Presentations | TBA |  |  |

# Project-oriented Risk List

|Risk name (value)  | Impact     | Likelihood | Description |
|-------------------|------------|------------|-------------|
|Unable to install custom firmware (27) | 3 | 9 | Firmware is locked: no known access to debugger (sdb) and no SD card slot  |
|Lack of team availability (24) | 6 | 4 | There is a possibility that there will be scheduling issues down the road which could lead to a loss of productivity |
|Brick the Echo Dot  (20) | 10 | 2 | It is possible to brick the Echo Dot when installing firmwares.  A custom firmware install, or root method, could brick the Echo Dot |
|Unable to find potential network vulnerability (18) | 3 | 6 | There may be no network-based vulnerabilities | 
|Unable to find potential vulnerability in Skills (16) | 2 | 8 | The custom coding skills API may have no vulnerabilites |

# User Stories

As a normal user, I want to be able to give a request to Alexa so that I can get a response, without anyone else hearing me.

As a normal user, I want to leave my Echo Dot alone without any requests being sent.

As a normal user, I want to download a useful skill that I can take advantage of.

As a developer, I want to be able to make a skill that users can find useful.

As an Amazon employee, I want to be able to put out a firmware update to the Echo Dot without someone else being able to overwrite it maliciously.

# Use/Misuse Case Diagram
![Use/Misuse Case Diagram](/Echo Dot Use+Misuse Case Diagram v1.png)

# Resources/Technology Needed
|Resource  | Dr. Hale needed? | Investigating Team member | Description |
|-------------------|---------|---------------------------|-------------|
|Another Echo Dot v2| Possibly | All | Having another Echo Dot v2 will allow more team members to work independently on the project  |
|Alexa Voice Remote| Yes | All | The Bluetooth Alexa Voice Remote may be vulnerable and is worthy of investigation  |
|WiFi Pineapple| Yes | James | For testing man-in-the-middle attack possibilities |
|Android Debuggers| No | Matt | Look into Android debuggers |
|Android Rooting| No | Matt | Look further into rooting the Echo Dot v2|
|Some way to setup airgapped testing lab| No | James | Setup a dedicated area for testing |
|Skills coding | No | Tim | Look into ways skills could be used to penetrate Echo Dot v2 |

# First Sprint Plan
https://trello.com/b/lrGlLkCc/echo-dot-project-main

# Team Members
* James Autry - jhautry
* Tim Gekas - tgekas
* Matthew Sutton - nfiniteecho
