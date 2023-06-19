**Translation:**
[中文(简体)](/readme/readme_chs_cn.md)
 | English
 | [Français](/readme/readme_fre_fr.md)
 | [Deutsch](/readme/readme_ger_de.md)
 | [Indonesia](/readme/readme_ind_id.md)
 | [Italiano](/readme/readme_ita_it.md)
 | [日本語](/readme/readme_jpn_jp.md)
 | [Português (Brasil)](/readme/reamde_por_br.md)
 | [Русский](/readme/readme_rus_ru.md)
 | [Español](/readme/readme_spa_xm.md)
 | [Türkçe](/readme/readme_tur_tr.md)
 
# swgoh-comlink-for-github
 This repo is used to get data from SWGoH Comlink and store it on GitHub so it can be used with personal projects without requiring hosting Comlink on a server. 
 
To get started follow the steps listed below.

## Step 1
***Go to GitHub and [Signup for an account](https://github.com/signup)***. After creating your username and password it will ask you several questions after verifying your email. The first question asks how many people are on your team, select just you and click continue. On the next question screen you can just click continue. After this it will give you plan options, choose the Free Plan by clicking continue with free. 
 
## Step 2
Once you are signed in ***Fork this repository*** by clicking the Fork option in the top right corner of the window between the Watch and Star options.

## Step 3
***Download and install [GitHub Desktop](https://desktop.github.com/)*** for your computer. After installation, open GitHub Desktop and sign-in.\
Next ***choose to Clone a Repository*** and clone the forked version you made of this repository. This will place a copy of it onto your computer.

## Step 4
***Download the latest binary file version of [SWGoH Comlink](https://github.com/swgoh-utils/swgoh-comlink/releases)*** to your computer.

## Step 5
***Download the latest version of PHP*** for your operating system if you do not already have it installed. The easiest way to get it installed with all needed files is to download [XAMPP](https://www.apachefriends.org/download.html).
### Steps to install PHP
1. To see if you have php installed you can either go to the command line using cmd.exe or Terminal and enter `php -v`. If you have it installed it will show you the version information.
2. Next, check to see if it has curl installed with it. Go to the command line using cmd.exe or Terminal and enter `php -i`. If you have it installed it will show you a section near the top labeled curl with the next line showing _cURL support = enable_.
3. If you do not have either of these you will need to install [XAMPP](https://www.apachefriends.org/download.html) from the link above choosing the appropriate operating system. During installation if you like, you can disable all additional options it shows such as perl, mySQL, etc. XAMPP is software that creates your own apache server locally on your computer and those options are just additional tools if you plan to use it for that, otherwise the base installation with php is sufficient.
4. After you have installed XAMPP into the directory you want it in, you may need to set the environment variable on your operating system to recognize it. In the search bar for Windows type Environment Variable and select the option that says Edit the system environment variables. Click Environment Variables at the bottom of the window that pops up. You need to slect the `Path` variable and then choose Edit. Add a ; followed by the full file path to the php.exe file. Do this to both the top box and the bottom box.
5. Go to the command line tool and enter `php -v` to verify php was installed correctly and is working.

## Step 6
***Open your command line tool*** by using _cmd.exe in the search box for windows_ or _terminal for linux/mac_. Run Comlink by entering the full file path followed by `--name "Comlink for GitHub"`. If you want you can use anything you want for the name.\
***Example:***\
`C:\Users\Kidori\Desktop\Swgoh Comlink\swgoh-comlink-1.3.0.exe --name "Comlink for GitHub"`

## Step 7
***Open a new command line tool window***. You will use this window to run the php scrpts to create/update the data in your repo. You do this by entering `php -r "require 'File Path'; function(arguments);"`. You will need to use the file path for your forked copy of this repo and then enter the function you would like to run.\
**Example**\
`php -r "require 'C:\Users\Kidori\Desktop\GitHub\swgoh-comlink-for-github\run.php'; getPlayerData(596966614);"`

### Available Functions for run.php
#### getPlayerData(allyCode, host, port, username, password)
Retrieves the player profile belonging to the ally code provided.\
**Parameters:**
```
 allyCode {string/integer} - the ally code of the player
 host {string} | Optional - the web address SWGOH Comlink is running on. Default is http://localhost:
 port {integer} | Optional - the port SWGOH Comlink is running on. Default is 3000
 username {string} | Optional - the access key or username needed by SWGOH Comlink if any
 password {string} | Optional - the secret key or password needed by SWGOH Comlink if any
```

#### getGuildData(ids, host, port, username, password)
Retrieves up to 2 guild profiles and guild rosters belonging to each specified ally code, player id, or guild id.\
**Parameters:**
```
 ids {array} - up to 2 ally codes, player ids, or guild ids to get guild profile(s) for
 host {string} | Optional - the web address SWGOH Comlink is running on. Default is http://localhost:
 port {integer} | Optional - the port SWGOH Comlink is running on. Default is 3000
 username {string} | Optional - the access key or username needed by SWGOH Comlink if any
 password {string} | Optional - the secret key or password needed by SWGOH Comlink if any
 ```

#### getGameData(filtered, allCollections, host, port, username, password)
Retrieves data collections related to different aspects of the game.\
**Parameters:**
```
 filtered {bool} | Optional - only returns the most useful data needed in each collection to reduce file sizes. The default is true.
 allCollections {bool} | Optional - returns all possible data collections the game uses. The default is false.
 host {string} | Optional - the web address SWGOH Comlink is running on. Default is http://localhost:
 port {integer} | Optional - the port SWGOH Comlink is running on. Default is 3000
 username {string} | Optional - the access key or username needed by SWGOH Comlink if any
 password {string} | Optional - the secret key or password needed by SWGOH Comlink if any
```

#### buildTerritoryBattles(lang)
Creates Territory Battles file.\
**Parameters:**
```
lang {string} | Optional - the language you want to use, not all data can be translated. Default is ENG_US
  OPTIONS: CHS_CN, CHT_CN, ENG_US, FRE_FR, GER_DE, IND_ID, ITA_IT,
               JPN_JP, KOR_KR, POR_BR, RUS_RU, SPA_XM, THA_TH, TUR_TR
```

## Step 8
After running the functions you will need to ***Publish the changes*** made to your cloned repo version ***using GitHub Desktop***. Go to _GitHub Desktop_ and _select the swgoh-comlink-for-github repo_ if it is not already selected. It should show a list of any files with changes pending, add a Summary for the changes and then _click Commit to main_. You will now need to _click Push origin_ to push the commits to GitHub.

## Step 9
You can now retrieve the updated information in Google Sheets by fetching the web address for the raw file. You can get this web address by clicking on the json file in your repo in an internet browser and clicking the Raw button at the top of the file editor window.\
**Example**\
`https://raw.githubusercontent.com/Kidori78/swgoh-comlink-for-github/data/platoons.json`
