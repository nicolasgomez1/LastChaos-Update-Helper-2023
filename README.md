# LastChaos-Update-Helper-2023
LastChaos Update Helper 2023

# Work Flow:
	1) Create Zip file
	2) Connect to FTP Server
	3) Change to Updates Path (FTPUpdates)
	4) Check if version.txt file exist
	5) If version.txt file NOT exist it will be created (With version: 1)	|	If file exist: Download it
	6) Upload Zip file
	7) If Zip Upload was successful: Upload new version.txt
	8) If version.txt Upload was successful: Change Version value in Database
	9) If table t_clientversion NOT exist: Create it	|	If table exist: Update a_min column value
	10) If Create/Update table fails: Revert version.txt file (Zip file will not deleted)
	
# Additionals if Repair System is checked
	11) Check if checklist.txt file exist
	12) If checklist.txt file NOT exist: Create it (Based in WorkingDirectory)	|	If file exist: Download it
	13) Rename Client files to ".bk_date_time" extension as postfix
	14) Upload new Client files
	15) If all Client files was Upload successfully: Upload checklist.txt
	16) If checklist.txt was Upload successfully: Delete .bk_date_time extension files	|	If checklist.txt Upload fails: Revert Client files with .bk_date_time files
