# Cloudflare (conditional) Dynamic DNS IP Updater
<img alt="GitHub" src="https://img.shields.io/github/license/K0p1-Git/cloudflare-ddns-updater?color=black"> <img alt="GitHub last commit (branch)" src="https://img.shields.io/github/last-commit/olgv/cloudflare-ddns-updater/main">

This script is used to update Dynamic DNS (DDNS) service based on Cloudflare! Access your home network remotely via a custom domain name without a static IP! Written in pure BASH.  

This fork is an amendment to [`cloudflare-ddns-updater`](https://github.com/K0p1-Git/cloudflare-ddns-updater) adding a function that checks if the IP has changed, as there is no need to update the DNS record since it already points to the correct IP address. This check helps reduce unnecessary API calls to Cloudflare and saves resources.  

On the other hand, if the IP is changing, the script will log this IP into the `current-ip.txt` file and go ahead with updating the DNS record using the new IP.


## Installation

```bash
git clone https://github.com/olgv/cloudflare-ddns-updater.git
```

## Usage
Update your details requested in lines 4-14 (4-8 are compulsory).
> Note: I had to use an `API Token` not a `Global API Key` in CloudFlare, and keep the script to `token` on line 5.

<br />

This script is used with crontab 
```bash
crontab -e
```
Specify the frequency of execution through crontab

```bash
# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of the month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of the week (0 - 6) (Sunday to Saturday 7 is also Sunday on some systems)
# │ │ │ │ │ ┌───────────── command to issue                               
# │ │ │ │ │ │
# │ │ │ │ │ │
# * * * * * /bin/bash {Location of the script}
```
<br>

Make sure you make both the script `cloudflare-template.sh` (or how ever you decide to call it) and the `current-ip.txt` file editable by using:
```bash
chmod +x cloudflare-template.sh
chmod +x current-ip.txt
```
and keep the two files together, in the same place.
## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Reference
This script is an amendment to the original [`cloudflare-ddns-updater`](https://github.com/K0p1-Git/cloudflare-ddns-updater). Support by [K0p1-Git](https://github.com/K0p1-Git) via PayPal [here](https://www.paypal.me/Jasonkkf).  
This script was also made with reference from [Keld Norman](https://www.youtube.com/watch?v=vSIBkH7sxos) video.

## License
[MIT](https://github.com/K0p1-Git/cloudflare-ddns-updater/blob/main/LICENSE)
