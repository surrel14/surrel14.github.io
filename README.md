# [GUIDE] COMPLETE GUIDE TO HOW TO SET UP AND USE THE DNS METHOD

## **Intro**


I recently bought a paid certificate but I decided to make this guide public in case anyone needs to set up and use the **DNS method**. This method **takes advantage of leaked enterprise certificates and uses a DNS to block Apple’s servers to check the validity status of these certificates**. 


> ### Downsides:

- Some apps may not work properly or at all (X app in my case didn’t let me login saying I was offline)
- Extensions mostly don’t work because some entitlements are missing in this type of certificates
- VPNs can only be used if set in a certain way
- Can be tricky to set up and keep it working. 


> ### Upsides:

- Notifications are working for some certificates (they need to have notifications entitlements, e.g. Tianjin Certificate does have it but Global Takeoff does not)
- Apps are properly installed
- Unlimited apps can be installed
- Apps don’t require to be refreshed
- Doesn’t require a PC/Mac to be set up and used.


I agree to say that **Sidestore+LiveContainer** is still the **most convenient free method for sideloading at the moment**; I’m not encouraging people to use one method over the other, this is not what this guide is intended for. My intention is to help people that for some reasons still prefer the DNS method, like for example, people who don’t have a PC/Mac or people who wants notifications working.
There are downsides and limitations on both DNS method and Sidestore+LiveContainer and is up to users decide which one fits better to their needs.


As far as I could see there are not many step by step guides about this method so I hope this can be useful to anyone. 

## **1. Set up NextDNS**


1. Open Safari and go to _[https://my.nextdns.io/](https://my.nextdns.io)_



2. Create an account and login 



3. Go to the _Denylist_ tab 


4. Add these domains: 
>
**_vpp.itunes.apple.com_**
>
**_appattest.apple.com_**
>
**_certs.apple.com_**
>
**_crl.apple.com_**
>
**_valid.apple.com_**
>
**_ocsp.apple.com_**
>
**_ocsp2.apple.com_**
>
**_ppq.apple.com_**
>
This last domain ( **_ppq.apple.com_**) will need to be used wisely but we will get to it later

5. Go to the _Setup_ tab, scroll down until you see _Setup Guide_ and be sure that _iOS_ is selected. Scroll down to _Configuration Profile_ and click on the link _apple.nextdns.io_

6. It will prompt you to install a Profile, allow it

7. Go to the _Settings_ app and click on the downloaded Profile, it’ll be called _NextDNS (xxxxx)_. Enter your passcode and install it

8. Go to _Settings>General>VPN & Management>DNS_ and select _NextDNS (xxxxx)_



## **2. Install Ksign/Esign**



Now that our DNS is set up we need to install Ksign or Esign using a leaked enterprise certificate:

1. Go to your NextDNS settings in Safari and under _Denylist_ turn off _ppq.apple.com_

2. Open a new tab in Safari and go to _[https://khoindvn.io.vn](https://khoindvn.io.vn)_

3. Scroll down until you see _Ksign Bypass Revoke_ or _Esign Bypass Revoke_ and click the first link from the top

4. If the app gets not installed properly delete it and try another link

5. If the app gets installed but says something like _“The integrity could not be verified”_ try another link 

6. If none of the links work you are likely blacklisted and the only way to fix that is to restore your device from iTunes/Finder or erase all content and settings from the device _Settings_ app (you can backup it first, then restore the backup after the device got erased)

7. If the app gets installed and prompt you with something like _”Unable to verify app: An internet connection is required…”_ then proceed to the next step 

 
8. Go to the _Settings_ app then go to _General>VPN & Management_ and click on the name of the certificate that got you the app installed and click on _Trust “Name of The Certificate”_ and then _Allow and Restart_

9. Your device will restart and you will be prompted to enter your passcode to allow the Profile installation

10. Once the device is on, click on the Ksign/Esign app, if it opens go to the next step, if it doesn’t, go to _Settings>General>VPN & Management_, click on the certificate name and then to _Verify app_. Now _Verify app_ will disappear and you should be able to open Ksign/Esign. If _Verify app_ doesn’t disappear that cert will not work and you will have to go back to step 4 and repeat the process

11. Go back to NextDNS settings in Safari and turn back on _ppq.apple.com_ then turn off your data/wifi for some seconds and then turn it on


## **3. Set up Ksign/Esign**


At this point we have the DNS set up and Ksign/Esign installed. Let’s say that the hard part is over. Now we will have to add the certificate file to our Ksign/Esign app:

1. Open _[this link](https://raw.githubusercontent.com/esigncert/khoindvn/refs/heads/main/document/DNS/Certs-Khoindvn.zip)_ and save the _.zip_ file somewhere in your _Files_ app. Open the _Files_ app to the directory you saved the _.zip_ file and simply click on it to unzip it

2. If you have KSign open it and go to _Settings>Certificates>Import KSign File_ and click on the _+_ in the top right corner. If you have Esign open it and go to _Settings>Import Resource_. Go to the directory where you previously unzipped the _.zip_ file and open the unzipped  folder. There will be two folders inside: _KsignCert_ and _EsignCert_. Open the folder that match with your installer (KSign/Esign) and select the certificate with the same name of the certificate that you previously trusted in the _Settings_ app under _General>VPN & Management_. If you have Esign a prompt  will pop up asking if you want to import certificate management, select _Import_ 


## **4. Install apps with Ksign/Esign**

Now we can finally start to install apps through Ksign/Esign:

1. Download the _.ipa_ file of the app you want to install 

2. Open Ksign/Esign. On Ksign go to the _Library_ tab and click on the _+_ button in the top right corner then select _Import from Files_ and select the _.ipa_ file you downloaded. On Esign go to the _File_ tab and click on the 3 points in the top right corner than click on _Import_ and select the _.ipa_ file you downloaded

3. Open Safari and go to the NextDNS settings (https://my.nextdns.io), go to the _Denylist_ tab and turn off _ppq.apple.com_. Then turn off your data/wifi by toggle airplane on for some seconds, then re enable data/wifi by turning airplane mode off

4. Open Ksign/Esign. If you have Ksign locate the app you previously imported in the _Library_ tab and select _Sign and Install_. If you have Esign go to _Settings>Sign Default Config_ and toggle _Install after signed_ on. Now go to the _App_ tab, click on the app you imported and select _Signature_

5. At this point the signing and installation process will start, click on _Install_ when prompted and go to the home screen. Wait for the app to be installed

6. When the app is installed go to Safari on the NextDNS settings in the _Denylist_ tab and toggle _ppq.apple.com_ on, then turn off your data/wifi for some seconds and then turn it on again

7. Go back to the home screen and open the app you just installed, it should open and be working. If for some reasons the app gets not installed (I don’t know the exact reason but it can happen) delete the app and Ksign/Esign, go back to section  _2_ and repeat the process with another link


IMPORTANT: Everytime you install an app _ppq.apple.com_ must be toggled off in the NextDNS settings. In the same way when the app has been installed toggle it on again. Everytime you turn _ppq.apple.com_ on data/wifi must be turned off for some seconds and then turned on again.


## **5. (Optional) Install and set up Feather**

For the ones, like me, that prefers Feather over Ksign/Esign here’s how to install it and set it up:

1. Open [this link](https://raw.githubusercontent.com/WhySooooFurious/Ultimate-Sideloading-Guide/refs/heads/main/raw-files/certificates.zip), download the _.zip_ file and save it somewhere in the _Files_ app

2. Open _Files_ app to the directory of the _.zip_ file, simply click on it, it will unzip it (it’ll be called _certificates_)

3. Download _Feather .ipa_ from the official GitHub and import it in Ksign/Esign and install it like you would install any other app

4. Open Feather and go to _Settings>Certificates_ then click on the _+_ in the top right corner 

5. Select _Import Certificate File_ and the file picker will open. Navigate to the _certificates_ folder we previously unzipped, open it and open the folder called with the same name of your certificate. Select the _.p12_ file and import it. Repeat the same process for by clicking on the _+_ in the top right corner and select _Import Provisioning File_, then select the _.mobileprovision_ file. In the _Password_ field enter the password which is _WSF_ and click _Save_. Now the certificate is imported

6. To install apps go to the _Library_ tab, click on the _+_ in the top right corner then _Import from Files_. Import your app, sign it and install it. Always remember to **turn off/on _ppq.apple.com_ and data/wifi evertime you’re installing an app**


### Optional (needed if you want ChatGPT working):
- Go to the _Whitelist_ section in your NextDNS settings in Safari and add this domains:

>

- _register.appatest.apple.com_

>

- _app.localhost.direct_

>

As long as you follow all the steps correctly you shouldn’t be revoked but keep in mind that this is a method that takes advantage of leaked enterprise certificates so can be unreliable. Check the certificate expiration date in Feather/Ksign/Esign; when you’ll be close (some days) to the expiration date you will have to find a new certificate. 


Thanks to u/hmd_msrf_k_ who helped me to make this guide as correct as possible. Hope this guide will be helpful, keep it up and good sideloading. 







