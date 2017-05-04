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
  * Attempt to be the first known group to root an Echo Dot v2 
  * Find a vulnerability that could lead to compromise of the Echo Dot through the Skills API
  * Develop secure usage practices by finding the threshold decibel levels required to converse with Alexa
* Provide a technical writeup concerning the results of our investigation into the Echo Dot, both for the benefit of Amazon so that they may patch any vulnerabilities we find, and for the rest of the security community, so that they may build off our work

### Table of contents
* [Proposed Project Timeline](#proposed-project-timeline)
  * [Gantt Chart](#gantt-chart)
  * [Tabular Project Timeline](#tabular-project-timeline)
* [Project-oriented Risk List](#project-oriented-risk-list)
* [User Stories](#user-stories)
* [Use/Misuse Case Diagram](#usemisuse-case-diagram)
* [Resources/Technology Needed](#resourcestechnology-needed)
* [Architectural Diagrams](#architectural-diagrams)
  * [Hardware Diagram](#hardware-diagram)
  * [Firmware Diagram](#firmware-diagram)
  * [Amazon Backend Diagram](#amazon-backend-diagram)
  * [Activity Diagrams](#activity-diagrams)
* [User Story Realizations](#user-story-realizations)
  * [User Story 1 Realizations](#user-story-1-realizations)
  * [User Story 2 Realizations](#user-story-2-realizations)
  * [User Story 3 Realizations](#user-story-3-realizations)
  * [User Story 4 Realizations](#user-story-4-realizations)
  * [User Story 5 Realizations](#user-story-5-realizations)
* [Assessment Activity Summary](#assessment-activity-summary)
* [Findings Summary](#findings-summary)
* [Final Report](#final-report)
* [Team Members](#team-members)

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
|**M3** Acivity Diagrams US4 & US5 | 4/6 | 5/4 | 4 Weeks|
|**M3** User Story Realization US4 & US5 | 4/6 | 5/4 | 4 Weeks|
|**M3** Write Final Report | 4/6 | 5/4 | 4 Weeks|
|**Milestone 3 Due** | 5/4 |  | **DUE** |
|**Final Presentations** | 5/4 |  | **DUE** |

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
|WiFi Pineapple| Yes | James | For testing man-in-the-middle attack possibilities |
|Android Debuggers| No | Matt | Look into Android debuggers |
|Android Rooting| No | Matt | Look further into rooting the Echo Dot v2|
|Some way to setup air gapped testing lab| No | James | Setup a dedicated area for testing |
|Skills coding | No | Tim | Look into ways skills could be used to penetrate Echo Dot v2 |

# First Sprint Plan
https://trello.com/b/lrGlLkCc/echo-dot-project-main

# Architectural Diagrams

### Hardware Diagram
![Hardware Architectural Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/Architectural%20Diagram%20-%20Hardware%20v2.png)

#### Hardware Main Specs

|Component| Name| Description|
|---------|-----------|-------|
|CPU|MEDIATEK ARM MT8163V|1.5Ghz Quad Core,64-bit, System-on-Chip|
|RAM|MICRON 6PA98|4GB, LPDDR3, Single Channel
|Wireless|MEDIATEK MT6625LN | 4-in-1: Wi-Fi, Bluetooth, FM, & GPS|
|IC Power Management|MEDIATEK MT6323LGA | Audio Amplifiers and LED Drivers|

#### Other Hardware

|Component| Description|
|---------|------------|
|Microphone x 7|Seven microphones are used to obtain verbal input for Alexa to process|
|Analog-to-Digital Converter (ADC)| Converts an analog verbal request into a digital form for processing|
|Digital-to-Analog Converter (DAC)| Converts digital signals into analog signals to send to the speaker for Alexa voice reply|
|Tactile Switch x 4| Used to mute, control volume, and perform an Alexa voice request
|Bluetooth Transmitter| Used in the Alexa Remote to transmit voice requests to the Echo Dot|
|Bluetooth Receiver |Used by Bluetooth speakers to receive transmissions from the Echo Dot to play music, or listen to an Alexa voice reply|

References: [Source](https://www.allaboutcircuits.com/news/teardown-tuesday-amazon-echo-dot-v2/)

### Firmware Diagram
![Firmware Architectural Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/Architectural%20Diagram%20-%20Firmware%20v1.png)

#### Voice & Action Processing Subsystem


##### Pyron Standup Recognizer

The folder ```\local\models\keyword\en-US\ALEXA``` contains configuration and working files for Alexa's voice recognition.  *Contents*:
* ALEXA.bg.hclg.pfst
* ALEXA.fg.hclg.pfst
* ALEXA.psvm
* ALEXA.scales
* final.trans
* finalQuant.mlp
* kw.cfg.json
* nonspeech_words.lst
* op.cfg.json
* pdf.counts
* phones.txt
* pryon.config
* pryon.manifest
* STOP.bg.hclg.pfst
* STOP.fg.hclg.pfst
* STOP.psvm
* STOP.scales
* train_glob.cmvn
* transform.mlp
* words.shrunk.txt.shrunk.txt

The files ```kw.cfg.json```, ```op.cfg.json```, ```pryon.config```,  ```ALEXA.psvm```, and ```STOP.psvm``` are interesting to point out.  The JSON files contain configuration for Alexa's hearing.  Here is a portion of ```kw.cfg.json```:
```json
...
op.cfg.json "ALEXA",
                "spotter": {
                    "classification-limits": {
                        "max-per-window": 3,
                        "stickiness": 0,
                        "window-size": 100
                    },
                    "classification-thresholds": {
                        "accept-threshold": 0.0,
                        "escalate-threshold": 1e+37,
                        "notify-threshold": -4.0,
                    },
                    "cleanup-period": 6000,
                    "escalation-period": 200,
                    "hmm-thresholds": {
                        "accept-threshold": 0.0,
                        "escalate-threshold": 1e+37,
                        "notify-threshold": 0.0
                    },
                    "lock-period": 40,
                    "probabilistic-hmm-near-miss": {
                        "decay": 15,
                        "enabled": true
                    }
                }
...
```

It implements ```op.cfg.json``` which contains rules for setting awake and sleep status for Alexa based on words she hears:
```json
{
  "awake": {
    "rules": [
      {
        "name": "ALEXA", 
        "next": "awake"
      }, 
      {
        "name": "STOP", 
        "next": "sleep"
      }
    ], 
    "timeout": {
      "duration": 175, 
      "next": "sleep"
    }
  }, 
  ...
  ```
  
```pryon.config``` defines variables for audio frequency, audio upscaling, and more.  Specifically, it contains settings that deal with keyword spotting:
```
...
# keyword spotter
search.decoder_type = "kaldi-key-phrase"
search.trans_filepath = "final.trans"
keyword_spotter.config_filepath = "kw.cfg.json"
keyword_spotter.op_config_filepath = "op.cfg.json"
keyword_spotter.emit_nearmiss = 1
...
```

```ALEXA.psvm``` at 1,173KB and ```STOP.psvm``` at 307KB appear to be voice models used to cross example for keyword detection.  The extension .psvm may stand for Pyron Standup Voice Model.


##### All Other Componenets for Voice & Action Processing Subsystem
|Component| Description|
|---------|------------|
|Save Audio|Saves the recorded audio to send and store in the Alexa app |
|Speech-to-Text|Processes your voice request into text to be stored in the Alexa app|
|Send Request| Uses Wi-Fi to transmit your request to Amazon servers using port 8080 or 443|
|Response Processing| The Echo Dot receives a response from Amazon servers and prepares to respond by storing data in memory|
|Alexa Verbal Response| The software action of executing Alexa's voice module to respond audibly to the user|

#### Firmware Update Subsystem

|Component| Description|
|---------|------------|
|Download Firmware| Downloads firmware updates from Amazon servers|
|Install Firmware| Begins the software process of updating firmware|
|Factory Reset Service| A binary exectuable that will begin to execute a factory reset

##### Firmware Scripts
```buttonHandler.sh``` contains logic for Echo Dot tactile button presses.  If a super long press, defined by variable ```$4 ```, is held then ```/system/bin/start factory-reset``` will be ran:
```shell
...
# Perform a factory reset if the factory reset button combination is hit for a super long press.
if [ "$3" = "factoryReset" -a $4 -eq 6 ]; then
    /system/bin/start factory-reset
fi
...
```

```updater-script``` contains commands to patch/extract system images.  It extracts the files ```lk.bin```, ```boot.img```, ```tz.img```, ```preloader.img```, and ```target.blocklist```:
```
getprop("ro.product.device") == "biscuit" || abort("This package is for \"biscuit\" devices; this is a \"" + getprop("ro.product.device") + "\".");
show_progress(0.750000, 0);
ui_print("Patching system image unconditionally...");
block_image_update("/dev/block/other-system", package_extract_file("system.transfer.list"), "system.new.dat", "system.patch.dat");
show_progress(0.050000, 5);
package_extract_file("boot.img", "/dev/block/other-boot");
show_progress(0.200000, 10);
package_extract_file("images/lk.bin", "/dev/block/other-lk");
package_extract_file("images/tz.img", "/dev/block/platform/mtk-msdc.0/by-name/tee1");
package_extract_file("images/preloader.img", "/dev/block/mmcblk0boot0");
package_extract_file("META-INF/com/amazon/android/target.blocklist", "/cache/recovery/last_blocklist");
set_metadata("/cache/recovery/last_blocklist", "uid", 0, "gid", 0, "mode", 0444, "capabilities", 0x0);
```

|Binary/Image| Description|
|---------|------------|
|lk.bin|File not found -- contained in script, but may be UBOOT universal boot loader for embedded systems, targeting different platforms including ARM|
|boot.img|Contains the kernel and ramdisk for Android|
|tz.img|File not found -- contained in script, but may be Trusted Zone for HBOOT bootloader|
|preloader.img| File not found -- contained in script: Unknown purpose|
|target.blocklist|Metadata (length, mount_point, dev, and sha1) used for setup of partitions for ```/boot```, ```/recovery```, ```/lk```, ```/tee1```, and ```/boot0```|


### Amazon Backend Diagram
![Backend Architectural Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/Architectural%20Diagram%20-%20Backend%20v1.png)


##### Alexa App Subsystem
|Component| Description|
|---------|------------|
|App Panel| User accessing the Alexa app through Android/Apple mobile application|
|Web Panel| User accessing the Alexa app through Amazon's web panel at:  http://alexa.amazon.com |
|Display Card| Amazon displays user request history in a linked-list format entitled "Cards."  Users can remove old cards from their request history from the Home page on the Alexa app. Other options provided by Cards:<ul><li>Replay Audio Request</li><li>Search Bing for Request</li><li>Did Alexa do what you wanted?</li><li>View Product Details</li><li>Search for Product on Amazon</li><li>Add Product to Amazon Shopping Cart</li><li>Add Product to Shopping List</li><li>View Applicable Terms</li><li>See additional results for Product on Amazon</li><li>Learn more (FAQ)</li></ul>|
|Execute Request| A user request will go through the Amazon app to be executed
|Store Request|A user request through Alexa will always be sent to the Alexa App Database to provide a user with their request history|

##### Amazon Alexa Database
|Component| Description|
|---------|------------|
|User's Alexa History|Each request is sent to the Alexa App Database to be stored so all request history can be viewed from any device via the Alexa Web App or Mobile App.|
|User's Alexa Settings|All Alexa app settings are stored to be synced across all devices|
|User's Voice Profile| Alexa can be trained to better recognize a user's voice.  It is assumed a user voice profile is kept by Amazon for better voice recognition across multiple devices|
|Other Entries|Smart home data, Group data (controlling multiple Amazon devices),  To-do list, etc.

##### Amazon Product Database
|Component| Description|
|---------|------------|
|Product Info|Stores product information such as price, quantity, size, color, etc.|
|Supplier Info|Stores product supplier information (e.g. Amazon or third party retailer selling through Amazon)|
|Shopping Cart|Stores user information regarding products in their shopping cart|
|Terms|Amazon products and services each have Applicable terms that are viewable when querying products through the Alexa app|

##### Amazon Account Database
|Component| Description|
|---------|------------|
|User Account Info|Stores Amazon account information for <ul> <li>Order History</li> <li>Login & Security Settings</li> <li>1-Click Ordering</li> <li>Language</li> <li>Message Center</li> <li>and more</li> </ul>|
|User Payment Info|Amazon Wallet user information includes: <ul> <li>Manage Payment Options</li> <li>Add Credit or Debit Card</li> <li>Amazon Credit Card</li> <li>Shop with Amazon Points</li> <li>Amazon Coins</li> <li>Gift Card Information</li> </ul>
|Amazon Prime Status|The Alexa app checks a user for Prime membership to enable certain premium features|
|Digital Content|Amazon accounts have access to digital content they purchase through Amazon|
|Other Entries|There is a wealth of other personal information that is stored by Amazon not listed here|

##### Third Party Account Database
Generalized descriptions: there are an abundance of default apps and downloadable Skills that interface with many third party services

|Component| Description|
|---------|------------|
|Account Information|User e-mails, usernames, passwords, used for user authentication & linking accounts|
|Preferences|User preferences for third party apps to sync with Alexa|
|Payment Information|Payment information may be stored on third party databases|
|Order Information|Ordering third party services may store a user's order information (e.g. Pizza orders or Uber driver location)|
|Other Entries|Other database entries exist that may be referenced by the Alexa app|

# Activity Diagrams

### User Story 1 Activity Diagram
Giving a verbal request to the Echo Dot
![First User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US1%20Activity%20Diagram%20v1.png)
### User Story 2 Activity Diagram
The Echo Dot Registration Process
![Second User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US2%20Activity%20Diagram%20v1.png)
### User Story 3 Activity Diagram
Enabling an Alexa Skill for use on the Echo Dot
![Third User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US3%20Activity%20Diagram%20v1.png)
### User Story 4 Activity Diagram
Developing an Alexa Skill using the Amazon Skills API
![Fourth User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US4%20Activity%20Diagram%20v1.png)
### User Story 5 Activity Diagram
goes here //NEEDS WORK

# User Story Realizations
<br>

## User Story 1 Realizations

User Story 1 focuses on gaining a fundamental understanding of the Echo Dot and Alexa App's functionality.  We have found that almost all traffic coming in or out of the Dot or Alexa App is encrypted using TLS v1.2 <br><br>

---

**Test: <a name="US1EchoDotNetworkAnalysis"></a>Echo Dot network analysis**

*Components Tested*: Firmware SendRequest and ResponseProcessing

*Purpose*: To determine if network traffic to and from the Echo Dot is transmitted securely during normal usage.

*Conducted*: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

*Results*: Network traffic to and from the Echo Dot is encrypted with TLSv1.2. 

See: [echodot-normal.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-normal.pcapng)

---

**Test: <a name="US1AlexaAppAnalysis"></a>Alexa App network analysis**

*Component Tested*: Backend ExecuteRequest & AppPanel

*Purpose*: To determine if network traffic to and from the Alexa app is transmitted securely during normal usage.

*Conducted*: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Alexa app on an Android phone. Wireshark was used to analyze the network traffic.

*Results*: Network traffic to and from the Alexa App is encrypted with TLSv1.2. 

See: [alexa-app.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/alexa-app.pcapng)

---

**Test: <a name="US1MITM"></a>Echo Dot man-in-the-middle attack**

*Components Tested*: Firmware SendRequest

*Purpose*: To determine if the encrypted traffic to and from the Echo Dot can be intercepted and logged by an attacker.

*Conducted*: Using sslsplit on the WiFi Pineapple to intercept and log the encrypted traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

*Results*: The Echo Dot fails to connect to the Amazon backend and gives a verbal message saying “Sorry, I’m having trouble understanding right now. Please try a little later”. The encrypted network traffic captured by Wireshark shows an “invalid certificate authority” alert. 

See: [echodot-sslsplit.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-sslsplit.pcapng)

---

**Test: <a name="US1DefaultApps"></a>Default Alexa Apps network analysis**

*Components Tested*: Firmware SendRequest

*Purpose*: To determine if any default apps transmit data securely during normal usage.

*Conducted*: nmap was used to find open ports when apps are running

*Results*: A port scan of the Echo Dot using ```nmap -p 1-65535 -T4 -A -v -Pn 172.16.42.213``` shows TCP port ```4070``` as open and accepting connections:
```
Scanning 172.16.42.213 [65535 ports]
Discovered open port 4070/tcp on 172.16.42.213
```
The Nmap scan report reveals that TCP port ```4070``` is used to connect to Spotify:
```
Nmap scan report for 172.16.42.213
Host is up (0.0024s latency).
Not shown: 49149 filtered ports, 16385 closed ports
PORT     STATE SERVICE VERSION
4070/tcp open  tripe?
| fingerprint-strings: 
|   DNSStatusRequest, DNSVersionBindReq, RPCCheck: 
|     HTTP/1.1 500 Server Error
|     Content-Length: 48
|     Date: Sat, 01 Apr 2017 16:38:56 GMT
|     Connection: close
|     Error 500: Server Error
|     Client closed connection
|   GenericLines, RTSPRequest: 
|     HTTP/1.1 500 Server Error
|     Content-Length: 35
|     Date: Sat, 01 Apr 2017 16:38:56 GMT
|     Connection: close
|     Error 500: Server Error
|     request
|   GetRequest, HTTPOptions: 
|     HTTP/1.1 400 
|     Content-Type: application/json
|     Content-Length: 72
|     {"status": 102, "statusString": "ERROR-BAD-REQUEST", "spotifyError": 0} ## here
|   SSLSessionReq, TLSSessionReq: 
|     HTTP/1.1 500 Server Error
|     Content-Length: 48
|     Date: Sat, 01 Apr 2017 16:39:04 GMT
|     Connection: close
|     Error 500: Server Error
|_    Client closed connection
```

---

## User Story 2 Realizations

User Story 2 focuses on gaining a fundamental understanding of the Echo Dot's default features and IoT capabilities. The Echo Dot registration process is also investigated. We have found that while most traffic coming in or out of the Alexa web panel is encrypted using TLS v1.2, the panel uses cookies and images which are not encrypted. <br><br>

**Test: <a name="US2Registration"></a>Echo Dot Registration network analysis**

*Components Tested*: Backend WebPanel

*Purpose*: To determine if network traffic to and from the Alexa web panel is transmitted securely during the Echo Dot registration process.

*Conducted*: Using dumpcap on Kali Linux to capture traffic to and from the Alexa web panel. Wireshark was used to analyze the network traffic. DWall on the WiFi Pineapple was also set to listen for any connections from the Echo Dot during registration.

*Results*: Network traffic to and from the Alexa web panel login page at ```https://alexa.amazon.com``` is encrypted with TLSv1.2. However, the Alexa web panel home page becomes ```http://alexa.amazon.com``` and some images are not encrypted.

See: [register-echodot.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/register-echodot.pcapng)

The following connections from the Echo Dot were observed during registration:

| Client | URL |
|---------|------------|
| 172.16.42.213 | http://spectrum.s3.amazonaws.com/kindle-wifi/wifistub-echo.html |
| 172.16.42.213 | http://apresolve.spotify.com/?client=2:5:0:71778395393884299 |

---
**Test: <a name="US2SetupMode"></a>Echo Dot Setup Mode network analysis**

*Components Tested*: Firmware SendRequest

*Purpose*: To determine if any default services transmit data securely during setup mode.

*Conducted*: nmap was used to find open ports when services are running

*Results*: A port scan of the Echo Dot using ```nmap -v -Pn 10.201.126.241``` shows TCP ports ```443``` and ```8080``` as open and accepting connections:
```
Scanning 10.201.126.241 [1000 ports]
Discovered open port 8080/tcp on 10.201.126.241
Discovered open port 443/tcp on 10.201.126.241
```
The Nmap scan report reveals that TCP port ```443``` is protected by tcpwrapper and TCP port ```8080``` is an HTTP proxy:
```
Nmap scan report for 10.201.126.241
Host is up (0.0041s latency).
Not shown: 998 filtered ports
PORT     STATE SERVICE    VERSION
443/tcp  open  tcpwrapped
8080/tcp open  http-proxy
| fingerprint-strings: 
|   DNSVersionBindReq, RPCCheck, Socks4, Socks5: 
|     HTTP/1.1 500 Server Error
|     Content-Length: 48
|     Date: Fri, 31 Mar 2017 20:37:37 GMT
|     Connection: close
|     Error 500: Server Error
|     Client closed connection
|   FourOhFourRequest, GetRequest: 
|     HTTP/1.1 405 Method Not Allowed
|     Content-Length: 63
|     Content-Type: text/plain
|     Connection: close
|     Allow: POST, OPTIONS
|     Error 405: Method Not Allowed - Unsupported HTTP Request Method
|   GenericLines, RTSPRequest: 
|     HTTP/1.1 500 Server Error
|     Content-Length: 35
|     Date: Fri, 31 Mar 2017 20:37:37 GMT
|     Connection: close
|     Error 500: Server Error
|     request
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     Content-Length: 0
|     Content-Type: text/plain
|     Connection: close
|_    Allow: POST, OPTIONS
| http-methods: 
|_  Supported Methods: POST OPTIONS
|_http-title: Site doesn't have a title (text/plain).
```

---

## User Story 3 Realizations
User Story 3 focuses on gaining a fundamental understanding of the Alexa App's Skills functionality. We have found that while most traffic coming in or out of the Alexa App is encrypted using TLS v1.2, the Alexa App uses cookies and images which are not encrypted. <br><br>

---

**Test: Alexa App Skills analysis**

*Components Tested*: Backend ExecuteRequest & AppPanel

*Purpose*: To determine if the Alexa App transmits data securely.

*Conducted*: DWall running on the WiFi Pineapple was set to listen for outgoing connections from the Alexa App.

*Results*: The following HTTP connections were found:

| Client | URL |
|---------|------------|
| 172.16.42.213 | http://alexa.amazon.com/manifest/pitangui.appcache |
| 172.16.42.213 | http://spectrum.s3.amazonaws.com/kindle-wifi/wifistub-echo.html |

The following cookie containing a session token was found:

| Client | Cookie |
|---------|------------|
| 172.16.42.213 | csrf=-596473391; session-id-time=2082787201l; session-token="zj1u6jHoFSW/IKiqqjg5oA7Pq6uetskaezQDXSOK44gc2ArEbaAhzMg5bL5JSwlONVD8MYB/HCT88//NsZj2rzh3bJh4u9vYEjdJ2FVOMpwqZiWEn5JUXB8TGWAr8q5rkXoXQc9aIN7erfLzFfF5LIz0xDya8chmCyCp438fY2B7Uxd7a6Zwi5xtvCcfqdDCzZP3W2A9ud8="; session-id=135-0434014-3121322; ubid-main=168-7802293-2301129; x-main="qwLIvaKNbaFe0EeqVW3DYH38WVbg@ipOYhoSuZtoYC0Y8RFqcVJQqdS849suCzSQ" |

Images from ```http://ecx.images-amazon.com``` are also transmitted by the Alexa App when the user taps the ```Skills``` menu. These images contain the thumbnail icons of the various Alexa Skills that are available.

---

**Test: Alexa Web Panel Session Hijack attack**

*Components Tested*: Backend ExecuteRequest & AppPanel

*Purpose*: To determine if the Alexa web panel is vulnerable to session hijacking.

*Conducted*: Using Cookie Cadger on Kali Linux to detect, intercept, and replay insecure HTTP GET requests and session cookies into the browser. 

*Results*: No recgonized session cookies were captured by Cookie Cadger.

## User Story 4 Realizations
**Test:** Alexa Skills API Assessment

*Components Tested*: Subsystem Amazon Alexa Database

*Purpose*: To determine if the Alexa Skills API can potentially be used to program a malicious skill.

*Conducted*: Using the Alexa Skills Kit (ASK) to see if the API potentially supports coding a malicious skill.

*Preface*: Amazon provides an AWS Lambda service for deploying Alexa Skills in the cloud. AWS Lambda is typically hosted on an Amazon Machine Image (AMI) running on Amazon's EC2 cloud platform. Developers of custom Alexa Skills also have the option to use their own cloud infrastructure to deploy the skill.

The following diagram shows the outline of the Alex Skill invocation process:
![ASK](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/ASK.png)

Amazon has created an Alexa App module to make it easier for developers to get starting coding their own Alexa Skills. This module can be found at: https://github.com/alexa-js/alexa-app

The alexa-app module parses HTTP JSON requests from the Alexa platform and builds the JSON response that is consumed by an Alexa-compatible device, such as the Echo.

This example shows how the alexa-app module can be used to build an Alexa Skill:

```
var alexa = require("alexa-app");
var template = require("./template.js");

var app = new alexa.app("test");

app.dictionary = {
  "names": ["Bob", "Jack", "Matt", "Mary", "Jane", "Bill"]
};

app.launch(function(request, response) {
  response.say("App launched!");
});

app.intent("sampleIntent", {
    "slots": { "NAME": "LITERAL", "AGE": "NUMBER" },
    "utterances": ["my {name is|name's} {names|NAME} and {I am|I'm} {1-100|AGE}{ years old|}"]
  },
  function(request, response) {
    setTimeout(function() {
      response.say("After timeout!").say(" test ").reprompt("Reprompt");
      response.send();
    }, 1000);
    // We are async!
    return false;
  }
);

app.intent("errorIntent", function(request, response) {
  response.say(someVariableThatDoesntExist);
});

// output the schema
console.log("\n\nSCHEMA:\n\n" + app.schema() + "\n\n");
// output sample utterances
console.log("\n\nUTTERANCES:\n\n" + app.utterances() + "\n\n");

// test pre() and post() functions
app.pre = function(request, response, type) {
  response.say("This part of the output is from pre(). ");
};
app.post = function(request, response, type, exception) {
  if (exception) {
    response.clear().say("An error occured: " + exception).send();
  }
};

// error example
app.request(template.errorIntent)
  .then(function(response) {
    console.log(JSON.stringify(response, null, 3));
  });

// async example
app.request(template.intent)
  .then(function(response) {
    console.log(JSON.stringify(response, null, 3));
  });

// synchronous example
app.request(template.launch)
  .then(function(response) {
    console.log(JSON.stringify(response, null, 3));
  });

// error example
app.messages.NO_INTENT_FOUND = "Why you called dat intent? I don't know bout dat";
app.request(template.missingIntent)
  .then(function(response) {
    console.log(JSON.stringify(response, null, 3));
  });

// error handler example
app.error = function(e, request, response) {
  response.say("I captured the exception! It was: " + e.message);
};
app.request(template.errorIntent)
  .then(function(response) {
    console.log(JSON.stringify(response, null, 3));
  });

```
The content of `template.js` shows how skills built with the alex-app module communicate requests to Amazon:
```
var template = {};
// LaunchRequest template
template.launch = {
  "version": "1.0",
  "session": {
    "new": true,
    "sessionId": "amzn1.echo-api.session.abeee1a7-aee0-41e6-8192-e6faaed9f5ef",
    "attributes": {},
    "application": {
      "applicationId": "amzn1.echo-sdk-ams.app.000000-d0ed-0000-ad00-000000d00ebe"
    },
    "user": {
      "userId": "amzn1.account.AM3B227HF3FAM1B261HK7FFM3A2"
    }
  },
  "request": {
    "type": "LaunchRequest",
    "requestId": "amzn1.echo-api.request.9cdaa4db-f20e-4c58-8d01-c75322d6c423"
  }
};
// IntentRequest template
template.intent = {
  "version": "1.0",
  "session": {
    "new": false,
    "sessionId": "amzn1.echo-api.session.abeee1a7-aee0-41e6-8192-e6faaed9f5ef",
    "attributes": {},
    "application": {
      "applicationId": "amzn1.echo-sdk-ams.app.000000-d0ed-0000-ad00-000000d00ebe"
    },
    "user": {
      "userId": "amzn1.account.AM3B227HF3FAM1B261HK7FFM3A2"
    }
  },
  "request": {
    "type": "IntentRequest",
    "requestId": "amzn1.echo-api.request.6919844a-733e-4e89-893a-fdcb77e2ef0d",
    "intent": {
      "name": "sampleIntent",
      "slots": {
        "NAME": {
          "name": "NAME",
          "value": "Matt"
        }
      }
    }
  }
};
// errorIntent template
template.errorIntent = {
  "version": "1.0",
  "session": {
    "new": false,
    "sessionId": "amzn1.echo-api.session.abeee1a7-aee0-41e6-8192-e6faaed9f5ef",
    "attributes": {},
    "application": {
      "applicationId": "amzn1.echo-sdk-ams.app.000000-d0ed-0000-ad00-000000d00ebe"
    },
    "user": {
      "userId": "amzn1.account.AM3B227HF3FAM1B261HK7FFM3A2"
    }
  },
  "request": {
    "type": "IntentRequest",
    "requestId": "amzn1.echo-api.request.6919844a-733e-4e89-893a-fdcb77e2ef0d",
    "intent": {
      "name": "errorIntent",
      "slots": {}
    }
  }
};
// missingIntent template
template.missingIntent = {
  "version": "1.0",
  "session": {
    "new": false,
    "sessionId": "amzn1.echo-api.session.abeee1a7-aee0-41e6-8192-e6faaed9f5ef",
    "attributes": {},
    "application": {
      "applicationId": "amzn1.echo-sdk-ams.app.000000-d0ed-0000-ad00-000000d00ebe"
    },
    "user": {
      "userId": "amzn1.account.AM3B227HF3FAM1B261HK7FFM3A2"
    }
  },
  "request": {
    "type": "IntentRequest",
    "requestId": "amzn1.echo-api.request.6919844a-733e-4e89-893a-fdcb77e2ef0d",
    "intent": {
      "name": "missingIntent",
      "slots": {}
    }
  }
};
// SessionEndedRequest template
template.session_end = {
  "version": "1.0",
  "session": {
    "new": false,
    "sessionId": "amzn1.echo-api.session.abeee1a7-aee0-41e6-8192-e6faaed9f5ef",
    "attributes": {},
    "application": {
      "applicationId": "amzn1.echo-sdk-ams.app.000000-d0ed-0000-ad00-000000d00ebe"
    },
    "user": {
      "userId": "amzn1.account.AM3B227HF3FAM1B261HK7FFM3A2"
    }
  },
  "request": {
    "type": "SessionEndedRequest",
    "requestId": "amzn1.echo-api.request.d8c37cd6-0e1c-458e-8877-5bb4160bf1e1",
    "reason": "USER_INITIATED"
  }
};
module.exports = template;
```

*Results*: <a name="SkillCertification"></a>All Alexa Skills must pass Amazon's skill certification tests in order for the skill to be publicly available on the Amazon skills store. These include Alexa policy tests, security tests, functional tests, and voice interface and user experience tests.

Amazon requires developers to provide testing instructions for the certification team, as shown in this dialog box:
![Certification](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/Certification.png)

Developers are also required to answer a variety of questions concerning the behavior of their Alexa Skill and if the skill collects personal information:
![Privacy](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/Privacy.png)


<a name="SkillPermissions"></a>Alexa Skills currently have access to a limited number of permissions: Device Address, List Read, and List Write. These permissions are configured in the Amazon Developer Portal. Once configured, the customer is prompted with a permissions card in the Alexa app to consent to provide the information requested when they enable the skill.
![Permissions](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/permissions.png)

After consent is obtained, a launch request from Alexa to the developer's Skill includes a user object that contains a consent token and device ID.

```
{
  "user": {
    "userId": "amzn1.ask.account.<userId_value>",
    "permissions": {
      "consentToken": "Atza|MQEWY...6fnLok"
    }
  },
  "device": {
    "deviceId": <device_id>,
    "supportedInterfaces": {}
  }
}
```

The device address permission has two options:
* Get Country and Postal Code - Gets the country and postal code associated with a device specified by deviceId.
```
Host: api.amazonalexa.com
Accept: application/json
Authorization: Bearer Atc|MQEWY...6fnLok 
GET https://api.amazonalexa.com/v1/devices/{deviceId}/settings/address/countryAndPostalCode
```
Example Response:
```
Host: api.amazonalexa.com
X-Amzn-RequestId: xxxx-xxx-xxx
Content-Type: application/json
{
  "countryCode" : "US",
  "postalCode" : "98109"
}
```
* Get Address - Gets the full address associated with the device specified by deviceId.
```
Host: api.amazonalexa.com
Accept: application/json
Authorization: Bearer Atc|MQEWY...6fnLok 
GET https://api.amazonalexa.com/v1/devices/{deviceId}/settings/address
```
Example Response:
```
Host: api.amazonalexa.com
X-Amzn-RequestId: xxxx-xxx-xxx
Content-Type: application/json

{
  "stateOrRegion" : "WA",
  "city" : "Seattle",
  "countryCode" : "US",
  "postalCode" : "98109",
  "addressLine1" : "410 Terry Ave North",
  "addressLine2" : "",
  "addressLine3" : "aeiou",
  "districtOrCounty" : ""
}
```

If a skill asks for address information for which the customer has not granted permissions, then the skill will receive an error. If the customer does not grant permission, the skill can provide a graceful fallback message and end the session. The table below represents possible responses to a request for address information.

| Response | Description |
|----------|-------------|
| 200 OK | Successfully got the address associated with this deviceId. |
| 204 No Content | The query did not return any results. |
| 403 Forbidden | The authentication token is invalid or doesn't have access to the resource. |
| 405 Method Not Allowed | The method is not supported. |
| 429 Too Many Requests | The skill has been throttled due to an excessive number of requests. |
| 500 Internal Error | An unexpected error occurred. |

The `Lists Read` and `Lists Write` permissions allow skills to integrate with Alexa lists. Alexa customers currently have access to two built-in lists: Alexa to-do and Alexa shopping. Customers can review or modify their Alexa lists using voice through the Echo Dot or via the Alexa App. For example, a customer can tell Alexa to add items to the shopping list at home, and then while at the store, view the items via the Alexa app, and check them off.

To access these list management capabilities, a skill requires a consent token specific to a customer to access that customer's Alexa lists. This token can be obtained with an in-session request, which is a customer voice request.

After customer consent is obtained, each voice intent request will include the customer consent token. An in-sesssion intent request to the skill from Alexa includes a `user` object that contains a consent token. The developer needs to retrieve this token value and use it in requests related to list management. The form of the full request is shown below.

```
{
  "version": "string",
  "session": {
    "new": true,
    "sessionId": "string",
    "application": {
      "applicationId": "string"
    },
    "attributes": {
      "string": {}
    },
    "user": {
      "userId": "amzn1.ask.account.<userId_value>",
         "permissions": {
             "consentToken": "Atza|MQEWY...6fnLok"
      },	
      "accessToken": "string"
    }
  },
  "context": {
    "System": {
      "application": {
        "applicationId": "string"
      },
      "user": {
        "userId": "amzn1.ask.account.<userId_value>",
           "permissions": {
             "consentToken": "Atza|MQEWY...6fnLok"
      },
        "accessToken": "string"
      },
      "device": {
        "deviceId": "string",	
        "supportedInterfaces": {
          "AudioPlayer": {}
        }
      },
      "apiEndpoint": "string"
    },
    "AudioPlayer": {
      "token": "string",
      "offsetInMilliseconds": 0,
      "playerActivity": "string"
    }
  },
  "request": {}
}
```

The list management capabilities provide create, read, update, and delete (CRUD) operations for the skill. This API exposes information about customer Alexa lists, and it supports list traversal. Each list item exposed through the API has properties such as value and itemId.

**List Management Domain:** https://api.amazonalexa.com/

| API | Method | URI Endpoint |
|-----|--------|--------------|
| Get lists metadata | GET | v2/householdlists/ |
| Get a list | GET | v2/householdlists/{listId}/{status} |
| Get a list item | GET | v2/householdlists/{listId}/items/{itemId} |
| Update a list item | PUT | v2/householdlists/{listId}/items/{itemId} |
| Create a new list item | POST | v2/householdlists/{listId}/items |
| Delete a list item | DELETE | v2/householdlists/{listId}/items/{itemId} |

* GetListsMetadata - Retrieves the Metadata for all customer Alexa lists.
```
GET: v2/householdlists/
Authorization: Bearer auth_token_for_customer
Content-Type: application/json
```
Response format:
```
HTTP 200 OK, on success
{
    "lists":
    [
        {
            "listId": // list id (String)
            "name": // list name (String)
            "statusMap": [
                { "status": "active" // (Enum) ,
                  "href": // active list items URL },
                { "status": "completed" // (Enum),
                  "href": // completed list items URL }
            ]
        }
    ]
}

HTTP 403 Forbidden, if customer authorization token is not valid/expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 500 Internal Server Error, if Alexa encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```

* GetList - retrieves a customer's Alexa list.
```
GET: v2/householdlists/{listId}/{status}
where {listId} is customer's list id and {status} is "active" or "completed"

Authorization: Bearer auth_token_for_customer
Content-Type: application/json
```
Response format:
```
HTTP 200 OK, on success

{
    "listId": // list id (String)
    "name": // list name (String)
    // default page size today is 100 and cannot be controlled by the client
    "items":
    [
	    {
            "id": // item id (String, limit 50 characters)
            "version": // item version (Positive integer)
            "value": // item value (String, limit 256 characters)
            "status": // item status (Enum: "active" or "completed")
            "createdTime": // created time (ISO 8601 time format w/time zone)
            "updatedTime": // updated time (ISO 8601 time format w/time zone)
            "href": // URL to retrieve the item (String)
         },
         ...
    ]
    "links": {
        "next": "v2/householdlists/{listId}/{status}?nextToken={nextToken}"
    }
}

HTTP 400 Bad Request, if input is malformed
{
    "message": // (String) (e.g., "invalid list items status)"
    "type": "InvalidInput"
}

HTTP 403 Forbidden, if a customer authorization token is not valid/expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 404 Not Found, if the list is not found
{
    "message": "list not found"
    "type": "ObjectNotFound"
}

HTTP 500 Internal Server Error, if Alexa encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```

* GetListItem - Retrieves a single item within a list.
```
GET: v2/householdlists/{listId}/items/{itemId}
where {listId} is customer's list id and {itemId} is the item id

Authorization: Bearer auth_token_for_customer
Content-Type: application/json
```
Response format:
```
HTTP 200 OK, on success

{
    "id": // item id (String)
    "version": // item version when it was read (Positive integer)
    "value": // item value (String)
    "status": // item status (Enum: "active" or "completed")
    "createdTime": // created time (ISO 8601 time format with time zone)
    "updatedTime": // updated time (ISO 8601 time format with time zone)
    "href": // URL to retrieve the item (String)
}

HTTP 403 Forbidden, if a customer authorization token is not valid/expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 404 Not Found, if the list or list item is not found
{
    "message": // error message (String) (e.g., "item is not found")
    "type": "ObjectNotFound"
}

HTTP 500 Internal Server Error, if Alexa encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```

* UpdateListItem - Updates an Alexa list item after the list item has been updated through the skill.
```
PUT: v2/householdlists/{listId}/items/{itemId}
where {listId} is customer's list id and {itemId} is the item id

Authorization: Bearer auth_token_for_customer
Content-Type: application/json

{
    "id": // item id (String)
    "version": // item version when it was read (Positive integer)
    "value": // updated item value (String, limit is 256 characters)
    "status": // item status (Enum: "active" or "completed")
}
```
Response format:
```
HTTP 200 OK, on success

{
    "id": // item id (String)
    "version": // updated item version (Positive integer)
    "value": // item value (String, limit is 256 characters)
    "status": // item status (Enum: "active" or "completed")
    "createdTime": // created time (ISO 8601 time format with time zone)
    "updatedTime": // updated time (ISO 8601 time format with time zone)
    "href": // URL to retrieve the item (String)
}

HTTP 403 Forbidden, if a customer authorization token is not valid, or has expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 404 Not Found, if the list or list item is not found
{
    "message": // error message (String) (for example, "item is not found")
    "type": "ObjectNotFound"
}

HTTP 409 Conflict, if the item versions mismatch
{
    "message": "item versions mismatch"
    "type": "Conflict"
}

HTTP 500 Internal Server Error, if Alexa has encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```

* CreateListItem - creates a new Alexa list item.
```
POST: v2/householdlists/{listId}/items

Authorization: Bearer auth_token_for_customer
Content-Type: application/json

{
    "value": // new item value (String, limit is 256 characters)
    "status": // item status (Enum: "active" or "completed")
}
```
Response format:
```
HTTP 201 OK, on success
Location: v2/householdlists/{listid}/items/{itemId}

{
    "id": // item id (String)
    "version": // item version (Positive integer)
    "value": // item value (String, limit is 256 characters)
    "status": // item status (Enum: "active" or "completed")
    "createdTime": // created time (ISO 8601 time format with time zone)
    "updatedTime": // updated time (ISO 8601 time format with time zone)
    "href": // URL to retrieve the item (String)
}

HTTP 403 Forbidden, if a customer authorization token is not valid/expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 404 Not Found, if the list is not found
{
    "message": "list is not found"
    "type": "ObjectNotFound"
}

HTTP 500 Internal Server Error, if Alexa encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```

* DeleteListItem - Deletes an Alexa list item.
```
DELETE: v2/householdlists/{listId}/items/{itemId}

Authorization: Bearer auth_token_for_customer
Content-Type: application/json
```
Response format:
```
HTTP 200 OK, on success

HTTP 403 Forbidden, if a customer authorization token is not valid/expired
{
    "message": "request is unauthorized"
    "type": "Unauthorized"
}

HTTP 404 Not Found, if the list or list item is not found
{
    "message": // error message (String)
    "type": "ObjectNotFound"
}

HTTP 500 Internal Server Error, if Alexa encountered a server error
{
    "message": // error message (String)
    "type": "InternalError"
}
```
In conclusion: Amazon only allows a limited number of permissions for use by Alexa Skills. Requests for these permissions will always prompt the customer to allow these permissions. Any Alexa Skill attempting to bypass this requirement receives a "request is unauthorized" response from the Alexa Skills API. This shows that the Alexa Skills API does not allow potentially malicious Skills to access information about the device or the customer directly.

## User Story 5 Realizations

**Test:** <a name="US5SPFlashTool"></a>Attempt to root the Echo Dot v2

*Components Tested*: Subsystem Firmware Update

*Purpose*: To determine if the Echo Dot v2 can be rooted at this time.

*Conducted*: Using MediaTek Smart Phone Flash Tools (SPFT) v5.1644, v5.1708, and v5.1712, and MTK (MediaTek) USB Driver Downloads to recognize, and attempt to root the software.  Scatter files to attempt a “readback” of data from the Echo Dot v2 to create a proper scatter file.

*Preface*: Blog author ダニエル on Medium.com had out some important tips for rooting the Echo Dot v2 in his blog post entitled [Exploring the Amazon Echo Dot, Part 2: Into MediaTek utility hell](https://medium.com/@micaksica/exploring-the-amazon-echo-dot-part-2-into-mediatek-utility-hell-b452f62e5e87).  We used his strategies to attempt rooting since our team is new to the Android rooting process.

*Results*: Overall, the Echo Dot v2 was not able to be rooted using SPFT because the SoC MT8163 required scatter file could not be found or generated.  Scatter files are file used to describe the loads of regions in a specific android device running MediaTek's ARM architecture.

Our strategy was to use third party MediaTek rooting tools to attempt to root the Echo Dot v2.  MediaTek device drivers were also required to recognize the Echo Dot v2.  Here is a look at the SPFT interface:

![SPFT Interface](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/SPFT%20Main.jpg)

A guess-and-check approach led to a working tool and driver combo of:
* SP Flash Tool v5.1708
* MT6577 USB VCOM Drivers

Other versions of SPFT and the MT VCOM drivers failed to produce any quality results.  

![Failures](https://github.com/jhautry/echo-dot/blob/master/images/Failures.jpg)

This is because when the Echo Dot v2 is connected to PC via USB, the MediaTek Preloader is only recognized for less than two seconds before Alexa enters setup mode.  Halting or stalling setup mode was not possible using any button combination.  Only the above software and driver combination was able to automatically halt the Echo Dot startup process.

Inside the SPFT software, a scatter file must be selected that aligns with the SoC contained within the hardware you wish to root.  A scatter file is a partition table that is used during the rooting process.  It can be created from *rooted devices* by using third-party tools, or by copying ```/proc/mtd``` to obtain block sizes for the partitions.  In an attempt to get the software working, a few alternative scatter files were used as test runs.  Here is the example scatter file for MediaTek SoC MT6575 that was used during testing:
```
PRELOADER 0x0
{
}
DSP_BL 0x40000
{
}
__NODL_NVRAM 0x100000
{
}
__NODL_SECCFG 0x400000
{
}
UBOOT 0x420000
{
}
BOOTIMG 0x480000
{
}
RECOVERY 0x980000
{
}
SEC_RO 0xe80000
{
}
__NODL_MISC 0xfa0000
{
}
LOGO 0x1000000
{
}
__NODL_EXPDB 0x1300000
{
}
ANDROID 0x13a0000
{
}
__NODL_CACHE 0x13aa0000
{
}
USRDATA 0x176a0000
{
}
__NODL_BMTPOOL 0xFFFF0050
{
}
```
Using the "Readback" function of SPFT, we attempted to rip the software from the Echo Dot.  However, we could not advance because using the MT6575 scatter file caused a "Chip type not match!" error.  The software actually stopped Alexa from booting up into setup mode.  If we had the correct scatter file, we would be on our way to rooting.  This is further than ダニエル has progressed during his exploration.

![Chip Type Not Match](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/Chip%20Type%20not%20Match.jpg)

In an attempt to obtain a MT8163 scatter file, we followed through to look for the ACER Iconia One 10 Tablet's (B3-A30) MT8163 SoC scatter file.  ACER product support led to the B3-A30 operating system update files at:
https://www.acer.com/ac/en/US/content/support-product/6839?b=1

Within the B3-A30 OS update files, we obtained ```scatter.txt``` which was not readable by the SPFT software:
```
preloader 0x0
pgpt 0x0
proinfo 0x80000
nvram 0x380000
protect1 0x880000
protect2 0x1280000
persist 0x1c80000
seccfg 0x4c80000
lk 0x4cc0000
boot 0x4d20000
recovery 0x5d20000
secro 0x6d20000
para 0x7320000
logo 0x73a0000
expdb 0x7ba0000
frp 0x85a0000
tee1 0x86a0000
tee2 0x8ba0000
kb 0x90a0000
dkb 0x92a0000
metadata 0x94a0000
system 0xb800000
cache 0x10b800000
userdata 0x12b800000
flashinfo 0xFFFF0084
sgpt 0xFFFF0004
```
This scatter file is in a different format than the previous scatter files.  It caused an error in SPFT:

![Bad Scatter File](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/Bad%20Scatter%20File.jpg)

We attempted to format ```scatter.txt``` into the correct format, but had no success.  Placing braces after each partition did not solve the problem.  We believe this ```scatter.txt``` to be used for update purposes only and, therefore, not useful for a fresh Android OS install.

![Scatter File Crash](https://github.com/jhautry/echo-dot/blob/master/images/Scatter%20Error.jpg)

Further Google searches led to no publicly available scatter files for a MT8163 SoC.  

A last attempt at finding MediaTek documentation led to a 9,975 page Chinese PDF.  We are not fluent in Chinese and failed to comprehend much within the PDF.

**Note: QUESTIONABLE LINK -- Browse at own risk (copy into browser):** https://yadi.sk/d/X0CLyxlduGccX

In conclusion: until a correct scatter file for SoC MT8163 is obtained, this method of rooting is not possible.

# Assessment Activity Summary

To assess the Echo Dot, we first developed five of the most common user stories for entities that interface with the Echo Dot.  User stories were used to determine what the Echo Dot does.  From these user stories, we assessed their standard procedures and developed acceptance criteria that need to be met to assure our user stories have no vulnerabilities.  To frame the threat landscape, we created a use/misuse case diagram to assess for potential vulnerabilities.  Additionally, an activity diagram was created for each user story to visualize the user’s actions as they complete a user story’s action.   These visual aids were all used to identify potential vulnerabilities in the Echo Dot’s functionality.  

After identifying weak-spots, we set forward to gain more information about how the device operates.  From our obtained knowledge of the product, we deduced there were three architectural layers to the Echo Dot: hardware, firmware, and the Amazon backend.  Architectural diagrams were created for each layer to further footprint how each layer’s components interface with each other.   By knowing how the components are organized, we planned methods of exploitation.  When one component is compromised other sibling components may follow. All this planning led us to the exploitation phase of our penetration test.  

From all our Echo Dot foot printing, we believed the device would be susceptible to network-based attacks.  Specifically, we were not confident in the Echo Dot’s protections from man-in-the-middle attacks.   All our user stories require network communications in some manner:
* US1 - End users give requests to Alexa that are then transmitted to Amazon for processing.  
* US2 - End users use the Echo Dot for wireless IoT administration of their home.
* US3 - End users download new skills to their Echo Dot to add features.
* US4 - Developers create new skills and upload them to Amazon’s servers.
* US5 - Amazon pushes a firmware update to the Echo Dot.
It was concluded that network-based exploitation would be one of our most likely avenues of exploitation. We obtained a Wi-Fi pineapple for network-based pentesting.

Another avenue of exploitation was via Amazon’s Skill API.  We theorized that it could be possible to code malicious skills using the Alexa Skills Kit.  Vulnerable code or functions in the skills kit could be deployed in a malicious fashion to exploit an end user.

Our final avenue of exploitation was to obtain root access to the Echo Dot to identify is full capabilities.  Preliminary research led us to believe this was not possible at the current time.  The bootloader is locked down and Amazon is not releasing its key.  However, the Echo Dot is can be flashed via MediaTek Android Smartphone Flashing Toolkits given the proper data.  We obtained the MediaTek tools for firmware based exploitation.

# Findings Summary

### Network Findings
Almost all traffic to and from the Echo Dot v2 is encrypted using TLS v1.2.  A man-in-the-middle attack using SSLsplit failed to net any results.  We do not possess Amazon’s private-key and were unable to strip encryption.  We have evaluated that the Echo Dot v2 properly secures all network traffic from eavesdroppers. 

![Network Findings Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/images/Network%20Results%20Diagram.png)

### Skills API Findings

The Alexa Skill API provides a limited set of permissions that Skills can access. The end user always receives a permission request via the Alexa App when they enable a developer's Alexa Skill. The following table summarizes the permissions.

| Permission | Description | Exploitable? | Reason | 
|------------|-------------|--------------|--------|
| Device Address | Allows access to end user's full address, or country and postal code. | No | This permission can only expose the physical address if the end user provides that information. The end user can also restrict the address information to only the country and postal code.  |
| List Read | Allows read-only access to the Alexa to-do and shopping lists. | No | This permission only allows read-only access to the shopping and to-do lists. |
| List Write | Allows read-write access to the Alexa to-do and shopping lists. | No | This permission does not allow Skills to actually order anything, only to add/remove items from the shopping and to-do lists. |

All Alexa Skills must also pass the Amazon Skill Certification requirements in order to be published and made available for end users to enable. These requirements include answering questions about the behavior of the Skill and providing testing instructions for the certification team.

Since all Alexa Skills are tested by the Amazon certification team before being put into production, and given the limited permissions that Alexa Skills have access to, it is unlikely that a developer could create an Alexa Skill with malicious intent.

### Root Access Findings

| Rooting Method | Working? | Reasoning? | Workaround? |
|----------------|----------|------------|-------------|
| Bootloader | No |Amazon has locked down the bootloader.  Fastboot getvar all shows unlock_status: false|None – wait until Amazon releases the unlock files|
|MediaTek Smart Phone Flash Tools|No|Unable to acquire proper scatter file for flashing|Buy a product with the same MT8163 V/B System-on-Chip and rip its scatter file to apply to the Echo Dot.|

The Echo Dot v2 has a bootloader that is locked down.  There is no access to common Android rooting tools like Android Debugging Bridge (adb). Until Amazon releases the unlock files for the bootloader another method must be used.   

The Echo Dot v2 uses MediaTek hardware that includes a low-level USB preloader.  This preloader can be used with MediaTek Flashing Tools to flash different firmware. We attempted to use the MediaTek Smart Phone Flash Tools to rip the firmware to see what is going on inside, but failed because we did not have the proper scatter file.  Scatter files are partition specifications required for the flashing tools to execute. The Echo Dot requires a scatter file for the MT8163 V/B SoC.  A scatter file from another MT8163 needs to be ripped and applied to the Echo Dot v2.

# Final Report
link here

# Team Members
* James Autry - jhautry
* Tim Gekas - tgekas
* Matthew Sutton - nfiniteecho
