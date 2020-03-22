# Script to auto renew/confirm noip.com free hosts

[noip.com](https://www.noip.com/) free hosts expire every month.
This script auto click web pages to renew the hosts,
using Python/Selenium with Chrome headless mode.

- Platform: Debian/Ubuntu Linux, no GUI needed (tested on Debian 9.x/10.x); python 2.x/3.x
- Ver: 0.7
- Ref: [Technical explanation for the code (Chinese)](http://www.jianshu.com/p/3c8196175147)
- Updated: 21/03/2020
- Created: 04/11/2017
- Author: loblab
- Modifications by: Demix

![noip.com hosts](https://raw.githubusercontent.com/loblab/noip-renew/master/screenshot.png)

## Usage

1. Run setup.sh and set your noip.com account information,
2. Run noip-renew.sh, check result.png (if succeeded) or error.png (if failed)

For docker users, check Dockerfile, docker-compose.yml, crontab-docker-host.

Check confirmed records from multiple log files:

``` bash
grep -h Confirmed *.log | grep -v ": 0" | sort
```

## Remarks

The script is not designed to renew/update the dynamic DNS records.
Check [noip.com document](https://www.noip.com/integrate) for that purpose.
And most wireless routers support noip.com.
You can also check [DNS-O-Matic](https://dnsomatic.com/) to update multiple noip.com DNS records.

## History

- 0.7 (23/03/2020): Code tidyup and improved efficiency (Removed number of hosts and automatically get this)
- 0.6 (23/03/2020): Improved support for Raspberry Pi (Raspbian Buster) & Changes to setup script.
- 0.5 (05/01/2020): Support raspberry pi, try different "chromedriver" packages in setup script.
- 0.4 (14/01/2019): Add num_hosts argument, change for button renaming; support user agent.
- 0.3 (19/05/2018): Support Docker, ignore timeout, support proxy, tested on python3.
- 0.2 (12/11/2017): Deploy the script as normal user only. root user with 'no-sandbox' option is not safe for Chrome.
- 0.1 (05/11/2017): Support Debian with Chrome headless.
