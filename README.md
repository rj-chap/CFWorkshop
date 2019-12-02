# CFWorkshop
This repo contains the slides and files required for my DefCon 27 (2019) and CactusCon 8 (2019) "Understanding and Analyzing Carrier Files" Workshop. Get it gurl!

**The malware samples for this workshop are located at:**
**https://incidentresponse.training/cfworkshop_samples.zip**
- The zip file password is: dc27workshop

```
remnux@remnux:~/cfworkshop$ ls
1a73585dc90551822b772e3bab61a856a3ed8377b2e71326ce1b946a43cfa1f2
3777e556ddbafa08d7dcb35876bc47ee1226a8ad7d014d94ec5c6f6fc191a34d
62a83453d87810a25cf7ef7952f8cbed211064f2de4e7e39ddcff42c8c855759
ad4a9c91b33217062c18b9945088150947cb127cd65962baa98fbd5c8eb8a18d
dd55a7a66df1ab791cccb06ba0c7da9ae9f7670bee673b4ee2df4fd21909ca07
f6e9515a3e2e9afc1a5ced7002ea19ceffab1bc2f7cc5cd4bbf86d22aa93057a
remnux@remnux:~/cfworkshop$ zip -e cfworkshop_samples.zip *
Enter password: 
Verify password: 
  adding: 1a73585dc90551822b772e3bab61a856a3ed8377b2e71326ce1b946a43cfa1f2 (deflated 44%)
  adding: 3777e556ddbafa08d7dcb35876bc47ee1226a8ad7d014d94ec5c6f6fc191a34d (deflated 23%)
  adding: 62a83453d87810a25cf7ef7952f8cbed211064f2de4e7e39ddcff42c8c855759 (deflated 17%)
  adding: ad4a9c91b33217062c18b9945088150947cb127cd65962baa98fbd5c8eb8a18d (deflated 5%)
  adding: dd55a7a66df1ab791cccb06ba0c7da9ae9f7670bee673b4ee2df4fd21909ca07 (deflated 40%)
  adding: f6e9515a3e2e9afc1a5ced7002ea19ceffab1bc2f7cc5cd4bbf86d22aa93057a (deflated 4%)
remnux@remnux:~/cfworkshop$ shasum -a 256 cfworkshop_samples.zip 
60a52e7b8d9c3d571a4eb3277b0ab801bc96b829a1f9d5b3de44f15019af74a0  cfworkshop_samples.zip
```

# Pre-requisites -- Can I Kick It? (Yes, You Can!)

This workshop will cover the file formats for both PDF and Office (e.g. docx) files. If you've never analyzed such a file for maliciousness, fear not! We'll be covering the basics. If you have programming/scripting experience, great. If not, don’t worry. If you have worked to deobfuscate code, fantastic. If not, meh.

At previous $dayjob, I ran a five-week onboarding program for our new hire SOC analysts. Even folks brand new to incident response are able to follow along and learn from this type of training.  I’ll work with anyone willing to push his or herself to learn some new skills.  To gain the most from the workshop, you will want to make sure that you are somewhat familiar with the following (as in, if you're not now, do some Googling!):

## JavaScript (JS) & Visual Basic for Applications (VBA)

We are going to be analyzing both JS and VBA code. If you have never touched either of these languages before, or you are not a programmer by nature, fear not.  Please contact me for some resources, or just hit YouTube/Google/whatever for some crash course action.

## Debugging

Big 'ol bonus if you're already familiar with debugging concepts such as setting breakpoints, stepping through code, etc.  If you have never run a debugger, go hit your favorite search engine and blah blah.  You know the drill.  I'll be covering the basics in the workshop, but you'll simply be more comfortable if you've had a little experience prior to the workshop.  No biggie if not.

## Virtual Machines (VMs)

We'll be using VMs to avoid infecting our host machines, as we'll be working directly with malicious documents.  If you've never used a VM before, you're going to have a bad time.  In such case, I recommend checking YouTube (or reaching out to me personally) for some resources on setting up a VM in a tool like VMware or VirtualBox.

# Materials & Equipment

## Hardware/Software
"P6 chip. Triple the speed of the Pentium."

To participate in the workshop, you don't need Acid Burn's laptop. However, you will want to bring a laptop equipped with the following:
- **The laptop will probably need at least 8GB of RAM**, as you'll need to be able to run your host OS along with two VMs.
- Please try to have a USB port available. I will have USB 3.0 drives with me the day of the workshop. These drives will be FAT-formatted (nothing fancy) and contain the files required for the workshop. I will also pop the files on to a cloud-based file sharing service ahead of the workshop for folks whom like to setup early.
- VM software!  You'll need software to run a VM, such as VMware or VirtualBox.  Doesn't matter if you're on a Mac with VMware Fusion, Windows, Linux, whatever.  As long as you can run a VM (and take at least one snapshot), we're solid!

# VM Setup

You will need to have 2 VMs ready to rock:

## Windows Malware VM

You will need a Windows malware VM (10 preferred, 7+ will work).
- If you do not have a Windows 10 malware analysis machine, please check out https://zeltser.com/free-malware-analysis-windows-vm/#step2
- Speaking of MS products, **you're going to need (in order to follow along with VBA file debugging), a copy (evaluation version works fine) of MS Office 2016+**. Version doesn't *really* matter, but the more recent the better.
- If you don't have an MS Office license, check out the MS Evaluation center for a copy of Office that you can use: https://www.microsoft.com/en-us/evalcenter/evaluate-office-365-proplus
- Please install PDFStreamDumper: http://sandsprite.com/blogs/index.php?uid=7&pid=57
- A hex editor of your choice! A few good options are HxD and 010 Editor (commercial, BUT AWESOME)
- e.g. HxD hex exditor: https://mh-nexus.de/en/hxd/
- Notepad++: https://notepad-plus-plus.org/

## REMnux VM

You will want an up-to-date copy of the REMnux VM: https://remnux.org/

- Please install ViperMonkey in REMnux: sudo -H pip install -U https://github.com/decalage2/ViperMonkey/archive/master.zip
- Otherwise, you're solid! All others tools we'll be using are installed by default in REMnux

### VMs available

If you REALLY cannot prep for the workshop (and damn you if this is the case), again, I'll have 20 or so USB 3.0 drives available with VMs that you can use. Please note that the VMs will be around 10GB+. Even though they are USB 3.0 drives, it will take a while to copy the required files to get setup. So... you know. PREP dang you!
