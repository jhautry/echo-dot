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

### User Story 3 Activity Diagram
Enabling an Alexa Skill for use on the Echo Dot
![Third User Story Diagram](https://raw.githubusercontent.com/jhautry/echo-dot/master/US3%20Activity%20Diagram%20v1.png)

# User Story Realization

### User Story 1 Realization
Writeup here:

Component Tested

Purpose

How the Test was Conducted

Results Discovered from Test

Link to Trello Card

### User Story 2 Realization
Writeup here:

Component Tested

Purpose

How the Test was Conducted

Results Discovered from Test

Link to Trello Card


### User Story 3 Realization
Writeup here:

Component Tested

Purpose

How the Test was Conducted

Results Discovered from Test

Link to Trello Card

# Milestone 3 Planning
https://trello.com/b/hllck0Nz/echo-dot-milestone-3-kanban


# Team Members
* James Autry - jhautry
* Tim Gekas - tgekas
* Matthew Sutton - nfiniteecho
