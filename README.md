# Dynamic Analysis of Malicious 3rd Party Software

> [!WARNING]
> Do not recreate at home. Some PUPs (Potentially Unwanted Programs) can escape VMs and infect the Host Device. While rare, this is a real possibility.

## Abstract
The purpose of this lab is to further the Cybersecurity field by providing Threat Intelligence on various 3rd party software. 
The range of software analyzed include but are not limited to: AV Antirus, iWinGames, Minecraft 1.16.2 Torrent, Comodo Dragon Chromium Browser, and CC Cleaner 7.
Analysis was conducted in a sandboxed Windows 10 Virtual Machine through Virtualbox Hypervisor. Monitoring was done through Task Manager and Resource Monitor as well as analyzing system changes or alerts during and after installation. Windows Defender and its' associated security measures were disabled to test the detection rate of web-installed Anitviruses and the full effect of installed PUPs.
Most installed PUPs utilized software bundling, prompting the user to install other software. "AV Antivirus" and "Avast Antivrus" had an estimated 2/3~ detection rate of downloaded Malware and or suspicious files. However, "RAV Endpoint Detection" had the highest accuracy of all three web-installed Antiviruses. This software was able to detect approximately 3x~ the amount of Malware and or suspicious files as the other two.

## Table of Contents
[Lab Environment and Components](#lab-environment-and-components)


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
        <summary>Click to see detailed Video Game Software Entries</summary>
        
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
