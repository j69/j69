# Mac tuning

##  → System preferences → Security
* disable Location Services
* disable Analytics
* disable Advertising

##  → System preferences → Battery
* disable Power Nap

##  → System preferences → Software Update
* disable Automatic update and only checks for update and install system data and security updates

## install [cool desktop saver](//github.com/pedrommcarrasco/Brooklyn/releases/download/1.0.0/Brooklyn.saver.zip)

## edit [hosts](http://winhelp2002.mvps.org/hosts.htm) file
  * sudo nano /etc/hosts
  * sudo killall -HUP mDNSResponder

## Show hidden files and folders in Finder
defaults write com.apple.finder AppleShowAllFiles -bool TRUE && killall Finder

## Allowing text selection in Quick Look/Preview in Finder by default
defaults write com.apple.finder QLEnableTextSelection -bool TRUE && killall Finder

## tune mouse speed
defaults write -g com.apple.mouse.scaling 12.0

## Automatically quit printer app once the print jobs complete
defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true

## Save to disk, rather than iCloud, by default? (y/n)"
defaults write NSGlobalDomain NSDocumentSaveNewDocumentsToCloud -bool false

## Prevent Time Machine from prompting to use new hard drives as backup volume?
defaults write com.apple.TimeMachine DoNotOfferNewDisksForBackup -bool true

## Disable local Time Machine backups? (This can take up a ton of SSD space on <128GB SSDs)
hash tmutil &> /dev/null && sudo tmutil disable local

## echo "Enabling UTF-8 ONLY in Terminal.app and setting the Pro theme by default
defaults write com.apple.terminal StringEncodings -array 4
defaults write com.apple.Terminal "Default Window Settings" -string "Pro"
defaults write com.apple.Terminal "Startup Window Settings" -string "Pro"

## Show hidden files in Finder by default? (y/n)"
defaults write com.apple.Finder AppleShowAllFiles -bool true

## Show dotfiles in Finder by default? (y/n)
defaults write com.apple.finder AppleShowAllFiles true

## Show all filename extensions in Finder by default? (y/n)
defaults write NSGlobalDomain AppleShowAllExtensions -bool true

# Terminal setup
* //brew.sh/
* brew cask install iterm2

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

# Remains of applications
Abandoned settings:
* ~/Library/Preferences
* ~/Library/Application Support/[AppName]
* ~/Library/Containers/[AppName]/Data/Library/Preferences

The cache related files are located in
* ~/Library/Caches или /Library/Caches
* ~/Library/Containers/[AppName]/Data/Library/Caches/[App Name]
* ~/Library/Saved Application State
