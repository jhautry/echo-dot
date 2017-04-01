**Test: Echo Dot port scan - normal mode**

Components Tested: Echo Dot v2, Wi-Fi

Purpose: To determine if any open TCP ports exist on the Echo Dot during normal usage.

Conducted: Using nmap to scan the Echo Dot with the “Intense scan, all TCP ports” option.

Results Discovered: TCP port 4070 is open on the Echo Dot during normal usage. This port appears to be used for Spotify on the Echo Dot.

[echodot-allTCP.xml](https://github.com/jhautry/echo-dot/blob/master/port-scans/echodot-allTCP.xml)

**Test: Echo Dot port scan - setup mode**

Components Tested: Echo Dot v2, Wi-Fi

Purpose: To determine if any open TCP ports exist on the Echo Dot during setup mode.

Conducted: Using nmap to scan the Echo Dot using the “Intense scan” option.

Results Discovered: Ports 8080 and 443 are open on the Echo Dot during setup mode. Port 8080 appears to be an HTTP proxy service and the service running on port 443 appears to be protected by tcpwrapper.

[echodot-setup-intense.xml](https://github.com/jhautry/echo-dot/blob/master/port-scans/echodot-setup-intense.xml)
