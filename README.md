![Lava Logo](LAVA/Assets/trapLogo.png)

# LAVA (Lightweight Antivirus Application) v3.1

##### Note: While we encourage anyone interested to explore our code and project as well as fork our project, it not intended to replace a professional piece of antivirus software and comes with no guarantees or warranty of any type. While we strive to produce the best possible software, the user assumes all risk as specified in the license agreement.

### What is LAVA?

LAVA is an academic project created by four undergraduate students at Hofstra University for a software engineering course (CSC 190). Built based on the open source ClamAV (https://www.clamav.net) using libClamAV, LAVA is a GUI-based application that offers the many anti-malware features. 

### Features (As of v3.1)
* **Full GUI Interface**
  * The user interface is completely visual, so the user should not need to interact with the command line interface. In fact, one LAVA initialized, the command line interface will disapear, leaving no distractions or clutter.
* **Types of Scans**
  * Complete Scan
     * Scans all attached drives and their subdirectories
  * Advanced Scan
     * Scans user-specified files and directories
  * Quick Scan
     * Scans all directories in "Antibody File" (Locations.LavaAnti) 
       * Antibody file starts with only the documents and desktop folders
       * As other scans such as Complete Scan or Advanced Scan detect malware, the "Antibody File" (Locations.LavaAnti) will be updated to contain the directories. If a parent directory is added, it will replace all its subdirectories. Likewise, subdirectories will not be added as they are already accounted for.
* **Scheduled Scans**
  * The user can opt to schedule a scan for later. When this happens a task will be added to Windows Task Scheduler to launch LAVA and have it scan the specified task at the specified time(s). The following parameters can be used:
    * Once
      * Runs the scan once at a specified date and time and deletes the task after it runs.
    * Daily
      * Runs the scan every X days starting on the specified date and time.
    * Weekly
      * Runs the scan every X weeks starting on the specified date and time. The start date determines the day of the weekday the scan will run.
    * Monthly
      * Runs the scan every X months starting on the specified date and time.
* **Database Updates**
  * Depending on which install method you use, the database may already be installed. If it is not (or is out of date), on startup LAVA will activate Freshclam (from ClamAV) to update or install the database files as needed with no inout from the user required.

### How was LAVA made?

LAVA was programmed in C++ as a Visual Studio 2019 command-line application. We opted to write LAVA in C++ to minimize overhead and maximize performance while still having access to certain higher-level features of a programming language.

Lava was made with the following projects:
* ClamAV (for malware dectection, databases and freshclam updates)
  * https://github.com/Cisco-Talos/clamav-devel
* Dirent (for directory traversal)
  * https://github.com/tronkko/dirent
* Nuklear (for GUI)
  * https://github.com/vurtun/nuklear
 
### How is LAVA licensed?

LAVA is licensed under the GNU GPLv3 agreement. The full agreement can be read here: (https://www.gnu.org/licenses/gpl-3.0.en.html)
