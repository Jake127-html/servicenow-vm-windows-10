# Dynamic Analysis of Malicious 3rd Party Software

> [!WARNING]
> Do not recreate at home. Some PUPs (Potentially Unwanted Programs) can escape VMs and infect the Host Device. While rare, this is a real possibility.

## Abstract
The purpose of this lab is to further the Cybersecurity field by providing Threat Intelligence on various 3rd party software. 
The range of software analyzed include but are not limited to: AV Antirus, iWinGames, Minecraft 1.16.2 Torrent, Comodo Dragon Chromium Browser, and CC Cleaner 7.
Analysis was conducted in a sandboxed Windows 10 Virtual Machine through Virtualbox Hypervisor. Monitoring was done through Task Manager and Resource Monitor as well as analyzing system changes or alerts during and after installation. Windows Defender and its' associated security measures were disabled to test the detection rate of web-installed Anitviruses and the full effect of installed PUPs.
Most installed PUPs utilized software bundling, prompting the user to install other software. "AV Antivirus" and "Avast Antivrus" had an estimated 2/3~ detection rate of downloaded Malware and or suspicious files. However, "RAV Endpoint Detection" had the highest accuracy of all three web-installed Antiviruses. This software was able to detect approximately 3x~ the amount of Malware and or suspicious files as the other two.

### Top of Page
[Click to go to the bottom of the page.](#bottom-of-page)

### Lab Environment and Components
<details>
<summary> Click to see Lab Environment and Components </summary>
    
* Hypervisor: VirtualBox Version 7.2.6 r172322
* OS: Windows 10 Home 22H2, Build: 19045.3803
* Network Adapter Configuration:
    ~~~
    Attatched to: Host-only Adapter
    Name: VirtualBox Host-Only Ethernet Adapter
    Adapter Type: Intel PRO/1000 MT Desktop (82540EM)
    Promiscuous Mode: Deny
    Mac Address: - 0 o 0 o 0 o 0 -
    Virtual Cable Connected [X}
    ~~~
* Hardware Resources:
    ~~~
    Base Memory: 7.792 Gb
    Number of CPUs: 8
    Processing Cap: 100%
    Paravirtualization Interface: Hyper-V
    Hardware Virtualization: [X] Nested Paging
    Video Memory: 128 Mb
    ~~~
</details>  


### Software/ Tools & Monitoring
* Performance Monitoring: Task Manager & Resource Monitor
* Domain Index: [ICANN](https://lookup.icann.org/en/lookup), [GoDaddy WHOIS](https://www.godaddy.com/whois)

## Methods for Simulated "Infection"
### Goal: Simulate a non-technical, negligent user searching the web for various "free" software.
* Used Chrome Browser, Google Search Engine with various keywords to quickly locate PUP sites.
* Windows Defender firewall and security measures were turned off.
  Keywords include:
  ~~~
  * free minecraft torrent download
  * free games download
  * chrome toolbar download
  * free cursors download
  * free virtual desktop pet download
  * free antivirus no malware
  * gta v apk download
  * free ram download
  ~~~
  Additionally, any time a new "Download" button appeared on screen, or a software was reccomended bundled with potenital PUPs, it was downloaded.

  <details>
  <summary>Click to see Video Game Software Related Entries</summary>
        
          Videogame Related Software:
  
          [A] Website: torrent4you.org/en/minecraft-1-16-2/
  
          Software: Minecraft 1.11, World of Tanks, World of Warships, War Thunder

          Description: [A] Advertises free torrent downloads mostly for popular Indie Game titles some larger games are included
          such as Dying Light 2: Stay Human and Far Cry 6.
          Minecraft 1.16.2 Torrent was downloaded and uTorrent was used for seeding. Sofrware did not install as advertised.
          Instead, Minecraft Version 1.11 (Released four years earlier) was installed.
          Additionally, a strange version, small-window version of the 2016 client opened and it was entirely in Russian.
          A UUID and Token string was automatically filled in, presumable a "legitimate" game token. World of Tanks, World of
          Warships, and War Thunder
          were offered and installed during installation. However, for one reason or another they did not function properly.

          Malware Detection: While untrustrable in a legitimate scenario, Avast and TotalAV Antiviruses immediately detected both the
          installer file and resulting application as Malware and quarantined it multiple times. Exception had to be made to continue.
  
          ICANN Lookup Result: Almost every field was littered with Redacted Values.
          Host Location: Tambov Oblast, Russia
          ISP: Key-Systems GmbH (Sankt Ingbert, Germany) +49 6894 9396850
          
  <img width="482" height="286" alt="53" src="https://github.com/user-attachments/assets/9092827d-fa12-4dd4-b54d-8c0b4d94eba6" />
  
        [B] Website: iwin.com/categories/games/free
  
          Software: Play iWin Games

          Description: Advertises itself as a browser-based gaming platform hosting (allegedly) over five-thousand games.
          Associated games are created and marketed towards children <14. The website heavily advertises various giveaways
          and a monthly ($6.99) subscription
          to access the entire catalog of games without advertisements. Upon visting, the website asks to download its'
          launcher software and requests access to
          apps on the device. Once installed it created a directory in the C:\ProgramFiles(x86) titled "iWin Games Manager V4."
          This directory holds the launcher files and games. Once you click "play" on the site a game "downloads" to your device.
          However, the location of locally stored game files were not located during testing.
          It is unclear as of yet, how games are locally stored and what the true purpose of installing this software is,
          outside of being a shortcut to the Website.
          Currently, it is assumed that the website uses the default installed files as an "engine" to run various games.
          Unfortunately, there were many issues directly related to playing these games. There was 1 instance of a game opening.
          Outside of that, everytime a game was "played" the website displayed a network issue, despite having a strong connection.
          It is not known if this is a direct result of the software detecting a Hypervisor and reacting.

          ICANN Lookup Result: Each field was replaced with "anonymized" information via proxy services to hide contact information
          in WHOIS directories. However, a LinkedIn page was found and contains the public profiles of high-level
          employees of iWin, Inc. https://www.linkedin.com/company/iwin-inc./ Estimated revenue is $6m per year.

          Malware Detection Summary:
          Total AV:
          Detection Name: TR/W32.Malware
          Suspected File: iWinGamesManager.exe
          Action: Quarantined
          Description: Upon installation of iWin Games Total AV IMMEDIATELY detected iWinGamesManager.exe as a Trojan
          targeting Windows 32 Systems and moved it into quarantine.
          
          Note: To summarize, iWin Games is a casual gaming development company that hosts a website offering several things.
          Offers include thousands of free games, giveaways, and a monthly $6.99 subscription for ad-free gameplay. A launcher
          file was suspected as Malware as soon as it was installed. It is of the author's opinion that iWin Games runs
          a  business model based on predatory marketing tactics towards children to profit. These predatory marketing
          tactics include large-banner giveaways all over the website, as well as monthly subscription advertisements.
          On top of this there were many trackers discovered on the website also found on similiar PUPs/ Malware sites.
          
     <img width="856" height="312" alt="77" src="https://github.com/user-attachments/assets/6404f1f1-55ed-4ca4-ad46-0176f19a7415" />

     <img width="827" height="352" alt="75" src="https://github.com/user-attachments/assets/ffcfa3f1-9ae0-4151-b30b-b9dc2b59d487" />

     <img width="824" height="398" alt="76" src="https://github.com/user-attachments/assets/54a581c5-987b-4afe-b2f3-96f2a459ad5e" />

     <img width="564" height="355" alt="78" src="https://github.com/user-attachments/assets/44abfdf0-f99d-4d03-8844-e423a4140284" />

    <img width="1006" height="622" alt="72" src="https://github.com/user-attachments/assets/664bc4b7-603c-435b-a67d-e53a3b5ba1c6" />

    <img width="1008" height="626" alt="73" src="https://github.com/user-attachments/assets/ab363807-9f97-4484-81ba-94339ad3cfc6" />

          [C]Website: pcapp.store/
            
          Software: PC App Store

          Description: Advertises itself as a software platform to download games, productivity software, entertainment and, 
          "exclusive deals." 

          ICANN Lookup: LIMITED INFORMATION. ICAAN reported a failure to process further information due to an error. The site host
          provider is Galcomm(http://www.galcomm.com.) Continuing investigations, it was found that the 
          abuse report number was found on another extremely suspicious site from the same host, Galcomm. 
          ANIMESUBID.XYZ returne the same abuse number as pcapp.store. 
          It was determined to be unsafe in continuing investigations on ANIMESUBID.XYZ unless inside a virtual machine,
          which would be outside the scope of this lab. 

          Malware Detection Summary:
          Total AV and Avast Antivirus both cancelled the installation shortly after running and quarantined multiple
          files every time (even with exceptions) all with the heuristic markers of Win64:MalwareX-gen [Adw]
          
          Note: Pc App Store was not able to be fully investigated, as numerous Antivirus issues prevented
          the installation from completing. Additionally, an online support agent admitted PC App Store is Adware.
          Even worse, their LinkedIn page had the following link as a website URL:
          https://www.linkedin.com/safety/notfound?_l=en_US

  <img width="1024" height="791" alt="83" src="https://github.com/user-attachments/assets/b0644cf2-aa94-4479-bc7b-f6e0d6b43aa2" />

  <img width="823" height="758" alt="84" src="https://github.com/user-attachments/assets/98f5505c-ce93-4bdb-a413-e4f734e722f6" />

</details>

<details>
<summary>Click to see Utility Software related Entries</summary>
       Utility Related Software:

    [D] Website: ccleaner.com/?srsltid=AfmBOoo1CdFKg-wManz5pTQSsjl4ryb8lhzgFJhVLfsWee_8_U2doANR

    Software: Ccleaner

    Description: Advertises itself as an optimization and utility software that can free up storage, 
    "boost your privacy." With a membership it can (allegedly) make your computer faster and free
    up storage on Google Drive and Microsoft OneDrive.

    Malware Detection: Not detected as Malware.
    
    ICANN Lookup Result:  All redacted for privacy.
    ITSNOTSKELETON-NETWORK Ltd.
    +1.2086851750

    Note:

    The conclusion of the software functionality is as follows; 
    
    The software has been determined to be ADWARE or a PUP.
    
    Only 11% of the Software is functional. This is due to the rampant "Trial or registration" requirement for in-app feature. Worse,
    Some features, even if they were completely free, did not properly function and resulted in errors, or endless stalling(In the case
    of the Software Updater.) It is advised to, instead of utilizing CCleaner, default to built-in Windows tools for performing every
    function this software displays, without installing anything, or even a membership.
    
    Functionalities Of Software
    1. Health Check: 3 Step proccess to maintain your Computer's health. 
        A. Privacy: Delete ALL temporary web browser data
        B. More Space: Delete ALL [basic] temporary system data.
        C. Resolve Issues: Speed up PC, update apps & drivers. Unusable without trial or membership.                      Efficacy unknown[X]
    
    2. Custom Clean: Scan your Computer for obsolete or malicious data; Junk, Browser, and Registry.
        Effective in remove obsolete data. Successfuly removed several malicious Registry Rules + backed up beforehand.   Efficient       [Y]
        One of the Registry rules deleted: 
        v2.30|Action|=Allow|Active=TRUE|Dir=In|App=C:\ProgramData\WindowsTask\AppModule.exe|Name=Shadow Service|

    3. Performance Optimizer: Puts high-performance apps to sleep. Unusable without trial or membership.                  Efficacy unknown[X]

    4. Driver Updater: Update or skip & ignore drivers. Unusuable without trial or membership.                            Efficacy unknown[X] 
    
    5. Software Updater: Operating System updates. Unusuable, update stalled for long periods of time.                    Efficacy unknown[X]

    6. Cloud Driver Cleaner: Save space in cloud storage. Unusuable without trial or membership.                          Efficacy unknown[X]

    7. Uninstaller: Uninstall software and oversee least used apps, or temporarily uninstall apps.                        Semi-efficient  [-]
    Temporary uninstall unusuable without trial or membership. Pointless, use Windows uninstall instead.
    
    8. Duplicate Finder: Scan for & delete duplicate files either generically or a specific folder. Unusuable.            Efficacy unknown[X]
    Both options did not function.

    9. Startup Manager: Manage startup apps and background processes. Offers same functionality as Task Manager.          Not efficient   [X]
    
<img width="997" height="647" alt="87" src="https://github.com/user-attachments/assets/54598406-934b-44e9-9619-2de7825cc759" />

</details>

<details><summary>Click to see Antivirus Software Related Entries</summary>

    [E] Website: avast.com/free-antivirus-download#pc
            
    Software: Avast Free Antivirus

    Description: Advertises itself as a free Antivirus with award winning protection.

    ICANN Lookup: 
    ITSNOTSKELETON-NETWORK Ltd.
    +1.2086851750

    Note: Even though this software should NEVER be installed in a legitimate scenario at least it provides a firewall log
    of all block incoming and outgoing connection.

    The conclusion of the software functionality is as follows; 
    
    The software has been determined to be Greyware.
    
    Problems:
    At first, Avast detected iWin Games as adware, then during a second round of manual scanning,
    it was NOT detected whatsoever.
    Smart scan DO NOT show up in scan history.
    Once a scan completes it warns in over 6 ways the device is at risk, however, it doesn't show what exactly
    is making the device vulnerable, even if you click on each warning. Resolving these warnings are not possible
    without a trial or membership. Additionally, if the warnings are skipped, the software goes right back to the home
    screen where it says "This computer is protected." 
    Most functions are blocked by a trial or membership.

    EICAR Detection Summary
    1. EICAR.COM       [PASS]
    2. EICAR.COM.TXT   [PASS]
    3. EICAR.COM.ZIP   [PASS]
    4. EICAR.COM-2.ZIP [PASS]

    Malware Detection Summary:
    Multiple PUPs were dected during stress testing and immediately quarantined, however
    iWin Games posed an excpeption. It was inconsistently detected. After initial
    installation it was  immediately detected as Adware. However, a later targeted scan of all 
    directories containg iWin Games files did NOT pose any warnings.
    
  <img width="938" height="627" alt="89" src="https://github.com/user-attachments/assets/ab622bba-015e-4926-a72c-d6c3835ef224" />

    [F] Website: totalav.com
            
    Software: Total AV 

    Description: Advertises itself as an award-winning Antivirus

    ICANN Lookup: 
    NA
    NA

    Note: UNKWN

    The conclusion of the software functionality is as follows; 
    
    The software has been determined to be UNKWN
    
    Problems: UNKWN
    

    EICAR Detection Summary
    1. EICAR.COM       [UNKWN]
    2. EICAR.COM.TXT   [UNKWN]
    3. EICAR.COM.ZIP   [UNKWN]
    4. EICAR.COM-2.ZIP [UNKWN]

    Malware Detection Summary:
    Several times during the course of this lab, Total AV "corrupted" and began 
    "repairing" the Antivirus Engine. Initially, the entry of this Antivirus was skipped
    to account for the excess waiting time. 
    However, 5+ hours since the last "break" and Total AV is still "repairing" itself.
    
    Any interaction with Total AV previously was done throughout several hours of the lab,
    before Antivirus entries began.


<img width="765" height="675" alt="90" src="https://github.com/user-attachments/assets/fb2afeb1-e34d-41c5-93bb-0726cc70a573" />



    [G] Website: reasonlabs.com/platform/products/endpoint-protection
            
    Software: RAV Endpoint Protection

    Description: Advertises itself as a Next-Gen Antivirus powered by AI-Cybersecurity. 

    ICANN Lookup: 
    Beaconmast
    +1.4806242599
    Registrant forms are far more transparent then every other ICAAN lookup within this lab.
    
    Note: 

    The Adblocking feature of RAV Endpoint is roughly 40% succesful on average.

    The conclusion of the software functionality is as follows; 
    
    The software has been determined to be Greyware
    
    Problems:
    Without going into the type of heuristics RAV Endpoint tracks, it only passed 3/4 EICAR tests.
    The concern here is the method of heuristics tracking. EICAR.COM.ZIP passed with a SEMI-PASS.
    However, EICAR.COM(-2).ZIP was a complete fail. 

    RAV Endpoint Detection did an automatic scan and detected a temporary file by Total AV to be 
    suspicious. Therefore, I scanned the exact directory using Avast Free Antivirus and there was nothing detected.
    The file path is:
    C:\Program Files (x86)\TotalAV\EndPoint Protection SK\coresdk\avcp-engine-1\is-DOLOJ.tmp.
    It is unknown at this time if this truly is a suspicious file or this is a simple accident.
    
    EICAR Detection Summary
    1. EICAR.COM       [SEMI-PASS] Removed on execution, NOT automatically quarantined. 
    2. EICAR.COM.TXT   [SEMI-PASS] Removed on execution, NOT automatically quarantined. 
    3. EICAR.COM.ZIP   [SEMI-PASS]Removed on execution, NOT automatically quarantined. 
    4. EICAR.COM-2.ZIP [FAIL] Complete absence of detection by RAV Endpoint Protection.

    Malware Detection Summary:
    Multiple PUPs were dected during stress testing and NOT quarantined. For unknown reasons
    the quarantine feature DID NOT work.


<img width="980" height="656" alt="91" src="https://github.com/user-attachments/assets/743cd7af-58ef-4e59-9b80-92a1e88405de" />

</details>

## Limitations
Although this Lab provides valuable insights into the perceived authenticity of free online software, several limitations must be aknowledged.

**First, the sample size was small.** This Lab focused on a few downloaded software on a single Virtual Machine. Therefore, the findings
may not be applicable to other experiences. Future research should aim to include either A.) Singularly focused on a software
and its' underlying code. B.) A larger, more diverse set of downloaded software across multiple Virtual Machines.

**Second, the data relied heavily on perceived experience.** While the user experience is important, it is subject to bias and can vary
from user to user. On the other hand, using software and tools to understand what is happening beneath the user experience can reveal
data that does **not** vary from user-to-user.

**Third, the Lab was completed by an Undergraduate who's credibility has not yet been established.** Although the Lab aims to analyze
software, the methods used could have been more rigorous. Methods included but not limited to are; decompiling code, examining logs, packets,
downloading a greater variety of free software, and testing across different Virtual Machines potentially utilizing alternative versions
of the Windows operating system.

**Finally, the duration of this lab was limited to a few weeks.** The time alotted may not be enough to account for potential long-term 
effects of continuously downloading free software online; Or further testing within that time-frame. 



### Bottom of page
[Click to go to the top of the page.](#top-of-page)
