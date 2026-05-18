## HTTP Web Enumeration Analysis

A large number of HTTP GET requests were captured targeting the DVWA web application.

## HTTP User-Agent Analysis

The Wireshark filter `http.user_agent` was used to inspect HTTP client identification strings.

The following User-Agent was identified:

Wfuzz/2.4

This indicates the use of an automated web fuzzing tool.

### Observed Behaviour

The attacker attempted to discover hidden or sensitive files by brute-forcing common filenames and directories, including:

- /.bashrc.php
- /.profile.php
- /_install.php
- /_media.php
- /~sys.php
- /2007.php
- /2012.php

### Analysis

The traffic shows systematic enumeration of the web server using a wordlist-based approach. This is typical of reconnaissance activity prior to exploitation.

## Evidence

https://github.com/rodrigoguadano/Network-Traffic-Analysis-with-Wireshark/blob/fff0cdeb558610cae95a8ca2e3342839c2679805/Screenshots/HTTP-Analysis.png

## Conclusion

The HTTP traffic indicates active web application reconnaissance against DVWA using automated fuzzing tools (Wfuzz), likely as part of a broader attack chain.
