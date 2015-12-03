# Nginx-1.9.3-anonymizer

This is a simple hack to fool HTTP scanners like HTTPrint and obscure webserver type and version. 
It should be applied in course with proper error page handling.

# What does it do?

It makes a following HTTPrint scan:

httprint v0.301 (beta) - web server fingerprinting tool
(c) 2003-2005 net-square solutions pvt. ltd. - see readme.txt
http://net-square.com/httprint/
httprint@net-square.com

Finger Printing on http://XXXXX:80/
Finger Printing Completed on http://XXXX:80/
--------------------------------------------------
Host: XXXXX
Derived Signature:
nginx/1.8.0
811C9DC5E2CE6926811C9DC5811C9DC5050C5D3294DF1BD04276E4BB811C9DC5
0D7645B5811C9DC5811C9DC5CD37187C66ABEB20811C9DC5811C9DC5811C9DC5
E2CE6926811C9DC5E2CE6923811C9DC5E2CE6927811C9DC5E2CE6926811C9DC5
E2CE6923E2CE6926811C9DC5E2CE6923E2CE69236ED3C2956ED3C295E2CE6923
E2CE69236ED3C295811C9DC5E2CE6927E2CE6923

Banner Reported: nginx/1.8.0
Banner Deduced: thttpd
Score: 79
Confidence: 47.59
------------------------
Scores: 
thttpd: 79 47.59
Microsoft-IIS/6.0: 78 45.37
Apache/1.3.26: 74 37.16
Apache/1.3.27: 73 35.26
Apache/1.3.[4-24]: 73 35.26
Apache/1.3.[1-3]: 73 35.26
Apache/2.0.x: 70 29.95
Apache/1.2.6: 63 19.59


look like this:


Host: XXXXX
Derived Signature:

811C9DC5E2CE6926811C9DC5811C9DC5811C9DC5811C9DC54276E4BB811C9DC5
0D7645B5811C9DC5811C9DC5CD37187C66ABEB20811C9DC5811C9DC5811C9DC5
E2CE6926811C9DC5E2CE6923811C9DC5E2CE6927811C9DC5E2CE6926811C9DC5
E2CE6923E2CE6926811C9DC5E2CE6923E2CE69236ED3C2956ED3C295E2CE6923
E2CE69236ED3C295811C9DC5E2CE6927E2CE6923

Banner Reported: -
Banner Deduced: Apache/1.3.26, thttpd
Score: 69
Confidence: 41.57
------------------------
Scores: 
Apache/1.3.26: 69 41.57
thttpd: 69 41.57
Microsoft-IIS/6.0: 68 39.35
Apache/1.3.27: 68 39.35
Apache/1.3.[4-24]: 68 39.35
Apache/1.3.[1-3]: 68 39.35
Apache/2.0.x: 65 33.16

Where it doesn't know whether it's IIS/nginx or Apache.
