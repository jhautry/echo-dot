**Test: Alexa App network analysis**

Components Tested: Alexa App

Purpose: To determine if network traffic to and from the Alexa app is transmitted securely during normal usage.

Conducted: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Alexa app on an Android phone. Wireshark was used to analyze the network traffic.

Results: Network traffic to and from the Alexa App is encrypted with TLSv1.2.

[alexa-app.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/alexa-app.pcapng)

**Test: Echo Dot network analysis**

Components Tested: Echo Dot v2, Wi-Fi

Purpose: To determine if network traffic to and from the Echo Dot is transmitted securely during normal usage.

Conducted: Using tcpdump on the WiFi Pineapple to capture network traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

Results: Network traffic to and from the Echo Dot is encrypted with TLSv1.2.

[echodot-normal.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-normal.pcapng)

**Test: Echo Dot man-in-the-middle attack**

Components Tested: Echo Dot v2, Wi-Fi

Purpose: To determine if the encrypted traffic to and from the Echo Dot can be intercepted and logged by an attacker.

Conducted: Using sslsplit on the WiFi Pineapple to intercept and log the encrypted traffic to and from the Echo Dot. Wireshark was used to analyze the network traffic.

Results: The Echo Dot fails to connect to the Amazon cloud and gives a verbal message saying “Sorry. I’m having trouble speaking right now”. The encrypted network traffic captured by Wireshark shows an “invalid certificate authority” alert.

[echodot-sslsplit.pcapng](https://github.com/jhautry/echo-dot/blob/master/packet-captures/echodot-sslsplit.pcapng)
