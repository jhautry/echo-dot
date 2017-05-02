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
* Pentest the Echo Dot's IoT capabilities.
* Pentest the Echo Dot and Alexa Voice Remote's bluetooth functionalities
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
|Alexa Voice Remote| Yes | All | The Bluetooth Alexa Voice Remote may be vulnerable and is worthy of investigation  |
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

# User Story Realization
<br><br>
## User Story 1 Realization

User Story 1 focuses on gaining a fundamental understanding of the Echo Dot and Alexa App's functionality.  We have found that almost all traffic coming in or out of the Dot or Alexa App is encrypted using TLS v1.2 <br><br>

---

**Test: Echo Dot network analysis**

*Components Tested*: Firmware SendRequest and ResponseProcessing

*Purpose*: To determine if network traffic to and from the Echo Dot is transmitted securely during normal usage.

*Conducted*: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

*Results*: Network traffic to and from the Echo Dot is encrypted with TLSv1.2. 

See: [echodot-normal.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-normal.pcapng)

---

**Test: Alexa App network analysis**

*Component Tested*: Backend ExecuteRequest & AppPanel

*Purpose*: To determine if network traffic to and from the Alexa app is transmitted securely during normal usage.

*Conducted*: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Alexa app on an Android phone. Wireshark was used to analyze the network traffic.

*Results*: Network traffic to and from the Alexa App is encrypted with TLSv1.2. 

See: [alexa-app.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/alexa-app.pcapng)

---

**Test: Echo Dot man-in-the-middle attack**

*Components Tested*: Firmware SendRequest

*Purpose*: To determine if the encrypted traffic to and from the Echo Dot can be intercepted and logged by an attacker.

*Conducted*: Using sslsplit on the WiFi Pineapple to intercept and log the encrypted traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

*Results*: The Echo Dot fails to connect to the Amazon backend and gives a verbal message saying “Sorry, I’m having trouble understanding right now. Please try a little later”. The encrypted network traffic captured by Wireshark shows an “invalid certificate authority” alert. 

See: [echodot-sslsplit.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-sslsplit.pcapng)

---

**Test: Default Alexa Apps network analysis**

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

## User Story 2 Realization

User Story 2 focuses on gaining a fundamental understanding of the Echo Dot's default features and IoT capabilities. The Echo Dot registration process is also investigated. We have found that while most traffic coming in or out of the Alexa web panel is encrypted using TLS v1.2, the panel uses cookies and images which are not encrypted. <br><br>

**Test: Echo Dot Registration network analysis**

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
**Test: Echo Dot Setup Mode network analysis**

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

## User Story 3 Realization
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

## User Story 4 Realization

**Test:**

*Components Tested*: 

*Purpose*: 

*Conducted*:

*Results*: 

## User Story 5 Realization

**Test:** Attempt to root the Echo Dot v2

*Components Tested*: Subsystem Firmware Update

*Purpose*: To determine if the Echo Dot v2 can be rooted at this time.

*Conducted*: Using MediaTek Smart Phone Flash Tools (SPFT) v5.1644, v5.1708, and v5.1712, and MTK (MediaTek) USB Driver Downloads to recognize, and attempt to root the software.  Scatter files to attempt a “readback” of data from the Echo Dot v2 to create a proper scatter file.

*Preface*: Blog author ダニエル on Medium.com had out some important tips for rooting the Echo Dot v2 in his blog post entitled [Exploring the Amazon Echo Dot, Part 2: Into MediaTek utility hell](https://medium.com/@micaksica/exploring-the-amazon-echo-dot-part-2-into-mediatek-utility-hell-b452f62e5e87).  We used his strategies to attempt rooting since our team is new to the Android rooting process.

*Results*: Overall, the Echo Dot v2 was not able to be rooted using SPFT because the SoC MT8163 required scatter file (partition table for rooting) could not be found or generated.

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

In an attempt to obtain a MT8163 scatter file, we followed through to look for the ASUS Iconia One 10 Tablet's (B3-A30) MT8163 SoC scatter file.  ASUS product support led to the B3-A30 operating system update files at:
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
**Note: QUESTIONABLE LINK -- Click at own risk -- Recommended airgapped PC**: https://yadi.sk/d/X0CLyxlduGccX

In conclusion: until a correct scatter file for SoC MT8163 is obtained, this method of rooting is not possible.

# Final Product
link here

# Team Members
* James Autry - jhautry
* Tim Gekas - tgekas
* Matthew Sutton - nfiniteecho
