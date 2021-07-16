# Mac for hackers

# Global Settings

## Hot corners
* botom left - launchpad
* bottom right - desktop
* top right - mission control

##  → System preferences → Security
* disable Location Services
* disable Analytics
* disable Advertising

##  → System preferences → Display
* disable Automatic brightness

##  → System preferences → Keyboard
* Shortcuts - enable Full Keyboard Access with TAB

##  → System preferences → Energy Saver
* disable Power Nap evrywhere
* disable Put hard disks to sleep

##  → System preferences → Software Update
* disable Automatic update and only checks for update and install system data and security updates

## install [cool desktop saver](//github.com/pedrommcarrasco/Brooklyn/releases/download/1.0.0/Brooklyn.saver.zip)

## edit [hosts](http://winhelp2002.mvps.org/hosts.htm) file
  * sudo nano /etc/hosts
### flush your Mac DNS cache
  * sudo killall -HUP mDNSResponder

## Show hidden files and folders in Finder
defaults write com.apple.finder AppleShowAllFiles -bool TRUE && killall Finder
## Copy selected text
defaults write com.apple.finder QLEnableTextSelection -bool TRUE && killall Finder
## tune mouse speed
defaults write -g com.apple.mouse.scaling 12.0

# Terminal setup
https://brew.sh/

## iterm2
* brew cask install iterm2
* `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
* brew install zsh-syntax-highlighting

## Install Powerlevel10k for your plugin manager for Oh My Zsh
`git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`

* nano ~/.zshrc
* `ZSH_THEME="powerlevel10k/powerlevel10k"`
* p10k configure

You could also assign custom keys in Prefs -> Keys
shift+left - move end of selection back
shift + right - move end of selection forward



## Install other apps
brew cask install
* slack
* telegram
* visual-studio-code
* spotify
* pycharm-ce
* tableplus
* postman
* speedtest-cli
* authy

## More fun
* sl fortune cmatrix

## Useful Terminal Commands
* calendar - `cal`
* calculator - `bc`
* show who is logged on and what they are doing - `w`
* Generate a Unique ID (UUID/GUID) - `uuidgen`
* Show network status - `netstat`

## Donwload files without browser
'curl -O https://get.videolan.org/vlc/3.0.3/macosx/vlc-3.0.3.dmg'

## Chrome settings
+ [uBlock Origin](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)
+ chrome://flags/ - `Turn off caching of streaming media to disk`


## Hackers part

### turn on system airport
* `ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport`
* `airport scan`
### turn off current WIFI
* `airport -z`
### enable monitoring and save the traffic into /tmp/airportSniff<random>.cap
* `airport sniff <channel number>`


### Mac startup key combinations

* Command (⌘)-R: Start up from the built-in macOS Recovery system. Or use Option-Command-R or Shift-Option-Command-R to start up from macOS Recovery over the Internet. macOS Recovery installs different versions of macOS, depending on the key combination you use while starting up. If your Mac is using a firmware password, you're prompted to enter the password.

* Option (⌥) or Alt: Start up to Startup Manager, which allows you to choose other available startup disks or volumes. If your Mac is using a firmware password, you're prompted to enter the password.

* Option-Command-P-R: Reset NVRAM or PRAM. If your Mac is using a firmware password, it ignores this key combination or starts up from macOS Recovery.

* Shift (⇧):  Start up in safe mode. Disabled when using a firmware password.

* D: Start up to the Apple Diagnostics utility. Or use Option-D to start up to this utility over the Internet. Disabled when using a firmware password.


# Remains of applications
Abandoned settings:
* ~/Library/Preferences
* ~/Library/Application Support/[AppName]
* ~/Library/Containers/[AppName]/Data/Library/Preferences

The cache related files are located in
* ~/Library/Caches или /Library/Caches
* ~/Library/Containers/[AppName]/Data/Library/Caches/[App Name]
* ~/Library/Saved Application State
