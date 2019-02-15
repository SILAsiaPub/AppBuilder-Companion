
## Sharing the app 

### Sharing the installer file

- Touch hamburger menu
- Touch Share App
- Touch `SHARE APP INSTALLER FILE`
  - If you have not given permission for the app to access the file system it will ask that permission once.

#### Share Without Internet:

- A list of sharing options shows up.
  - I used to use ShareIt for phone to phone transfer via wifi but don't now, as I don't like the permissions it asks for.
  - I have Xender that is a WiFi file transfer system too.
  - Bluetooth is an option but it is much slower than wifi transfer.

#### Share wih Internet
- You can choose email or social media
  - Some social media will not allow ZIP or APK files to be shared.
  
### Sharing the Play Store link.

- Touch hamburger menu
- Touch Share App
- Touch SHARE `LINK TO APP ON GOOGLE PLAY`
- You can choose one of your email or social media providers to send the link

### Sharing via a dedicated wifi Hot Spot

An easy way to share is via wifi hotspot. A number of options are avialable.

- Light Stream 
- Battery powered modified wifi router running BibleBox or LibraryBox
  - TP-Link TL-MR3020 needs external power supply  (Possibly out of production)
  - TP-Link TL-MR3040 has its own internal battery (Possibly out of production)

### Sharing from your phone via a web server.

#### If your phone is not rooted.

Various opions are available. If you have a choice, look for these features:
- The app must be able to pick a folder as the shared folder. Preferably including the SD card as an option.
- The app should show a file list if no index.html file is present.
- The page presented should be readable on a phone without zooming the interface.
- The file list should be mobile friendly
- Should only request `Read and write to external storage` and `Access Network State` 
- It is nice if you can change the port number. (Note: non-rooted phone cannot use a port number below 1025)
- suggested port: 1234
- Download a Web Server
  - Http Server by streamingnology
  - Tiny Web Server by Leonardo Javier Russo Communication
  - miniserver built on Termux and NodeJs. Not user friendly but best mobile interface.
  
| Feature | Http Server | Tiny Web Server | miniserver |
|--- |--- |--- | --- |
| Can choose source folder | Yes | Yes | Yes  |
| Show files when no HTML | Yes | Yes | Yes |
| File list shuold be readable| Yes | No | Yes
| File list should be mobile friendly | Just readable | unreadable must zoom | Great |
| Only request minimal permissions | Yes | Yes | Yes |
| Can change the port number | Yes | Yes | Yes |
| Setup | easy | easy with UTF-8 | complicated |

##### How to use

Need a sign or QR code for:
- The wifi hotspot name
- The URL ie 192.168.0.1:1234

Qre codes make it easy if they have a QR code reader.



#### If you have a rooted phone

- Install PirateBox app