# Linux Bing Wallpaper Shell Scripts

It sets Bing.com wallpaper of the Day as your Linux Desktop

supports XFCE4, GNOME3 and others, as well fallback to feh.

## Usage

Download these two scripts.

Put them somewhere (~/bin for example)

Change mkt varible in bing_wallpaper.sh to your market (valid values are: en-US, zh-CN, ja-JP, en-AU, en-UK, de-DE, en-NZ, en-CA)

Give the scripts execution permissions.

Make them autostart. (Google is your friend)

So next time you boot your computer for the first time a day, it'll run once.

Next boots it will run too, but do nothing.

## Easy commands

        mkdir -p ~/.local/bin/
        wget -P ~/.local/bin/ https://raw.githubusercontent.com/lowy/linux-bing-wallpaper/master/bingwallpaper 
        chmod +x ~/.local/bin/bingwallpaper
        
        # Add application startup items
        mkdir -p ~/.icons/
        wget -P ~/.icons/ https://raw.githubusercontent.com/lowy/linux-bing-wallpaper/master/bing.png
        mkdir -p ~/.local/share/applications/
        wget -P ~/.local/share/applications/ https://raw.githubusercontent.com/lowy/linux-bing-wallpaper/master/bingwallpaper.desktop 
        chmod +x ~/.local/share/applications/bingwallpaper.desktop
        
        # Default behavior
        ~/.local/bin/bingwallpaper -t #每日壁纸更新
        ~/.local/bin/bingwallpaper -w #一周壁纸巡览

        # First param is Market
        # Second param is true to exit immediately if you want to use a cron
        # (otherwise, script will sleep 24 hrs)
        ~/.local/bin/bingwallpaper -t true

## Example cron usage (crontab -e for your user)
```
# m h dom mon dow command
* * * * * ~/.local/bin/bingwallpaper -t true
```
