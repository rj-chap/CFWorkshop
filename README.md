# CFWorkshop
This repo contains the slides and files required for my DefCon 27 (2019) "Understanding and Analyzing Carrier Files" Workshop. Get it gurl!

# Where's the GOOD stuff?
In the days leading up to the workshop, this repo will be updated with step-by-step instructions for the workshop. Until that time, the slides will serve as a reference point for the general makeup of the workshop.

# What?
YEAH! Let's do this!

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
-- If you don't have an MS Office license, check out the MS Evaluation center for a copy of Office that you can use: https://www.microsoft.com/en-us/evalcenter/evaluate-office-365-proplus
- Python! You'll want to have Python installed (2.7.x preferred). I'll have an offline installer available on the USB drives should you need one (make sure you have that USB port available!)
- Please install PDFStreamDumper: http://sandsprite.com/blogs/index.php?uid=7&pid=57

## REMnux VM

You will want an up-to-date copy of the REMnux VM: https://remnux.org/

- All the tools we need for REMnux are installed by default. Thus, you simply need a working VM
