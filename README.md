# discover

## Host discovery scan with nmap. Read subnets from an excel spreadsheet and send an email once done.

Discover performs a host discovery scan with NMAP of IPv4 networks found in an excel spreadsheet column of multiple spreadsheets. 

Host discovery scan of each IPv4 network in a spreadsheet column of multiple spreadsheets.

IP-address or full CIDR syntax is needed: x.x.x.x/y, only one per cell. 

Once done, the scan result is sent as per email. 

An notification email is sent if the timeout is reached before the scan completed. 

## Howto

Edit discover.py and add your own To and From email addresses. Also add at least one SMTP server to send email through.

Nmap is started as root with sudo, so start sudo BEFORE the script to ensure a sudo sessions is cached:
```
$ sudo test
[sudo] password for user: 

$ python3 discover.py ../intersection/examples/france_without_paris.xlsx 
```


## The discover --help page

```
$ python3 discover.py --help
Usage: discover.py [OPTION]... <EXCEl_SPREADSHEET>...

Host discovery scan of each IPv4 network in a spreadsheet column of multiple
spreadsheets. IP-address or full CIDR syntax is needed: x.x.x.x/y, only one
per cell. Scan result is sent as per email once done. An notification email is
sent if the timeout is reached.

Options:
  -h, --help            show this help message and exit
  -n NETWORK, --network=NETWORK
                        Network data column
  -t TIMEOUT, --timeout=TIMEOUT
                        Timeout in seconds

Open Source MIT License. Written by Christian Angerbjorn
```

## Prerequisites

Discover is written in Python3. 

The following python3 packages are required to read excel .xlsx spreadsheets:
- openpyxl

## License
Open Source MIT License
