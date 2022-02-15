# Bitcoin Price Checker

I created a simple bash script to be run by Cron that checks the price of Bitcoin each hour during the work week (M-F 8-5). 

This script is designed to push a notification at the top of each hour that tells you what the price change of BTC has been over that hour.

Notifications have been tested in Pop!\_OS, so if you have any issues with it, you may have to tweak the crontab info. 

Additionally, there will be a file called "BitcoinPriceHistory" in your home directory that contains a maximum 24-hour price history. 

Push notification will not work without ```notify-send```.

## Installation Instructions

```git clone https://github.com/taplummer/BTCPriceChecker.git```

```cd BTCPriceChecker```

```./installer```

Once you've run the installer, there will be a new crontab job that runs Monday-Friday at each hour from 8 AM to 5 PM.

Happy HODLing!

## Modifying Crontab

```crontab -e```

This will pull up your user-specfic crontab. 

The installer script should've entered ```0 8-17 * * 1-5 XDG_RUNTIME_DIR=/run/user/$(id -u) bash ~/.BTCscript```

On some distros, you may need to change the ```XDG_RUNTIME_DIR=/run/user/$(id -u)``` part. Unfortunately, it's a bit of trial and error with cron pushing notifications, so your mileage may vary if the included configuration doesn't work.
