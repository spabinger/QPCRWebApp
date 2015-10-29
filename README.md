# QPCRWebApp
FAQ for the QPCR web application. [Pubmed](http://www.pubmed.org/19712446)

www.icbi.at/qpcr


## Installation: Troubleshooting
######JAVA problem######
* Possible solution:
The main sticking point was the location of JRE required by the software. I had to set the path for JAVA_HOME to the location of JRE within the JDK directory because the path ../server/jmv.dll was located there. The other issue was that you had to start the servers an administrator or they wouldn’t work.

######PostgreSQL problem######
When using a PostgreSQL version >9.0 the database needs to be adjusting using this command
```
ALTER DATABASE database_name SET bytea_output TO 'escape';
```
See: http://badrit.com/blog/2011/1/19/postgresql-9-bytea-type-problems#.VieYhXVSuko

######Suse problem######
We have experienced problems when installing QPCR on the Suse distribution (probably an issue with the Java installation). If possible, please use another distribution (e.g., Ubuntu).


## Installation: Checks
After installation there are a couple of things you could do to check if the system is running properly:
* Check if both QPCR and the Usermanagement system are up and running
* Try to log into the Usermanagement System and check if the QPCR account is still valid (Users -> show all -> application status)
* Check the log files for detailed error messages

## Installation: No credentials for databases (Step 7)
Error message: "Could not connect to the specified database"

Step 7 of the installation asks for database credentials (username and password).

Before starting the QPCR installer you need to have a running instance of a Postgresql or Oracle database and create two users (one for the usermanagement system and one for the QPCR system) to access it. In step 7 the username and pwd of these database users are requested.

Hint: check out
http://www.postgresql.org/download/windows
for a Windows installer.

## "Plate has no values to analyse" with LightCycler
For LightCycler users:
If you're getting a "Plate has no values to analyse" error message during parsing please make sure that the 
‘point index’ check box is checked when exporting the .xml file.

## Errors during parsing
**File could not be parsed**
Please make sure that you assign a name for all wells (especially when using Abi SDS). QPCR takes this name as sample name and uses it later in subsequent analysis steps.

**File Format not supported - Unexpected length of RAW section**
The SDS file seems to be corrupted. Please try to save it again and re-upload it into the QPCR application.

## Tutorial files appear to corrupted
If you either cannot download the tutorial files or cannot extract the zip file please download the files from
[tutorialFiles.zip](http://icbi.at/software/qpcr/downloads/tutorialFiles.zip)
and try it again.

## What qPCR machines are supported?
The following qPCR machines are supported by QPCR:
* **ABI 7000** (SDS file, exported component file, exported deltaRn file)
* **ABI 7500** (EDS file, exported file including Sample Setup and Amplification Data)
* **ABI 7900** (SDS file, exported clipped file)
* **LightCycler 2.0** (IXO file, exported Fluorescence history (over Cycles) as XML file)
* **LightCycler 480** (IXO file, exported Fluorescence history (over Cycles) as XML file)
For machines that are not supported please use the generic CSV format.

## 

