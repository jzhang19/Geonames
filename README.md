# Geonames
	Notes taken when working on getting all the countries, states, provinces, and cities. 
## Import geo location text files into MySQL database tables
### Step 1: Download Files  
[Geonames Org](http://download.geonames.org/export/dump/):
* [allCountries.zip](http://download.geonames.org/export/dump/allCountries.zip)
* [alternateNames.zip](http://download.geonames.org/export/dump/alternateNames.zip)
* [admin1CodesASCII.txt](http://download.geonames.org/export/dump/admin1CodesASCII.txt)
* [featureCodes_en.txt](http://download.geonames.org/export/dump/featureCodes_en.txt)
* [timeZones.txt](http://download.geonames.org/export/dump/timeZones.txt)
* [countryInfo.txt](http://download.geonames.org/export/dump/countryInfo.txt)

### Step 2: Run script to create schema



### Bugs:
* #### Error: 1290. --secure-file-priv option [Reference](https://stackoverflow.com/questions/32737478/how-should-i-tackle-secure-file-priv-in-mysql)
		1. SHOW VARIABLES LIKE 'secure_file_priv';
		2. Disable secure-file-priv. This must be removed from startup and cannot be modified dynamically. To do this check your MySQL start up parameters (depending on platform) and my.ini.

* #### Error: 1366. Incorrect integer value: "for column 'elevation' at row 1 [Reference](https://bugs.mysql.com/bug.php?id=18551)
		* set sql_mode = ''; -- empty string means 'traditional MySQL-mode'
		
* #### Error: 1300. Invalid utf8 character string: ''Afikanisitani,'Apekanikana,A Phu Han (Afghanistan),A Phú Hãn ' [Reference](https://stackoverflow.com/questions/766809/whats-the-difference-between-utf8-general-ci-and-utf8-unicode-ci)
		* Use utf8mb4_unicode_ci
		
* #### Error: 2013. Lost connection to MySQL server during query [Reference](https://stackoverflow.com/questions/10563619/error-code-2013-lost-connection-to-mysql-server-during-query)
		* Edit → Preferences → SQL Editor → DBMS connection read time out

