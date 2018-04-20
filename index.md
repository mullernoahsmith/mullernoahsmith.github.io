## Official Adobe Flash uninstaller a malware?

The first link on official Adobe website searching for Adobe Flash uninstaller is highly likely a malware.  The official Adobe website is linking to a DMG (and probably windows exe), that is likely a malware cross scripted on their official website. 

A number of tech websites including PC World, MacWorld, Apple Insider, Cult of Mac and even Google Search Card for the keyword "Flash uninstaller mac" leads to this malware link.

### How did you come to know this?

After temporarily using adobe flash for a day for an old application, I googled "remove flash mac" which led me to the official adobe page at https://helpx.adobe.com/flash-player/kb/uninstall-flash-player-mac-os.html. Once it was downloaded, I tried to open the DMG when something caught my eye. Thanks to Apple warning about unknown developers, I noticed DMG was downloaded from ezfyzz.graygeorge.win! Wait a minute - where did that come from!

I again downloaded the dmg and read the metadata a second time! The dmg had the same source ezfyzz.graygeorge.win!

### Investigating source

Next I checked if the website was correct or was a phishing website. The link was using https so I queried the certificate. 

```sh

❯ curl --insecure -v https://helpx.adobe.com 2>&1 | awk 'BEGIN { cert=0 } /^\* SSL connection/ { cert=1 } /^\*/ { if (cert) print }'
* SSL connection using TLSv1.2 / ECDHE-RSA-AES256-GCM-SHA384
* ALPN, server accepted to use http/1.1
* Server certificate:
*  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; OU=IS; CN=*.adobe.com
*  start date: Jan  5 00:00:00 2018 GMT
*  expire date: Jan  5 12:00:00 2019 GMT
*  issuer: C=US; O=DigiCert Inc; CN=DigiCert SHA2 Secure Server CA
*  SSL certificate verify ok.
* Connection #0 to host helpx.adobe.com left intact
```

The certificate of the link looked legit and signed by Digicert to be an official certificate. 
[Link](url) and ![Image](src)
For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mullernoahsmith/mullernoahsmith.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
