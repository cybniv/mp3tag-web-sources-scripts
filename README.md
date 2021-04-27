<h1 align="center">
 <br>
 <img src="https://www.mp3tag.de/images/logo.png">
 <br>
 Mp3tag Web Sources Scripts
 <br>
 <a href="https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg"></a>
 <a href="https://www.mp3tag.de/en/index.html"><img src="https://img.shields.io/badge/Program-Mp3tag-orange.svg"></a>
</h1>

<p align="center">
 <b>
 REQUIREMENT: Mp3tag v3.06b or above
 </b>
</p>

## Table of Contents
* [Description]()
* [Step-by-Step Instructions on Adding Web Sources Scripts to Mp3tag]()
* [Step-by-Step Instructions on Using Web Sources Scripts in Mp3tag]()
* [Commented-Out Tag Fields in the Web Sources Scripts]()
* [Questions About the Web Sources Scripts]()
  * [How do I change the purchasing country?]()
  * [How do I get a genre ID that is not listed in the web sources scripts?]()
  * [How do I get music metadata from a country of Apple Music or iTunes Store that is not available in the repository?]()
* [Additional Information]()
* [License]()

## Description
This repository contains web sources scripts for Mp3tag that will allow for the databases of Apple Music and the iTunes Store to be used to update music metadata. These web sources scripts for Mp3tag can automatically add tags to any song available on Apple Music and/or the iTunes Store. For these web sources scripts to work, the Apple Music or iTunes Store URL of a song is needed, which can be easily obtained by clicking on "Copy Link" in Apple Music or the iTunes Store.

The web sources scripts in this repository include some modifications that were made by me. The original web sources scripts without any of these modifications can be located at a forum called [Mp3tag Community](https://community.mp3tag.de/). Special thanks to [AreDigg on Mp3tag Community](https://community.mp3tag.de/t/ws-apple-music/51184) for making the original versions of the Apple Music and iTunes Store web sources scripts.

## Step-by-Step Instructions on Adding Web Sources Scripts to Mp3tag
1. Download Mp3tag from the official website ([Official Version](https://www.mp3tag.de/en/download.html) or [Beta Version](https://community.mp3tag.de/t/mp3tag-development-build-status/455))
2. Install Mp3tag on your device and open it
3. Download the web sources scripts from this repository
4. Move the **.inc** and **.src** files to `%appdata%\mp3tag\data\sources`

## Step-by-Step Instructions on Using Web Sources Scripts in Mp3tag
1. Open Mp3tag
2. Select the song(s) that you want to retrieve metadata for
3. Click on "Tag Sources" in the toolbar
4. Hover over Apple Music or iTunes Store
5. Select the country that you want to get your metadata from
6. Paste an Apple Music or iTunes Store URL into the text box
7. Click on "Next >"
8. Check if it is the correct album
9. Compare the bottom two boxes and check if your song(s) is/are in the right order/placement
10. Click on "OK" to complete the process

## Commented-Out Tag Fields in the Web Sources Scripts
There are three commented-out tag fields in these web sources scripts because these three tag fields will contain your personal information and will have to be edited by you. The three commented-out tag fields are the following: `ITUNESACCOUNT`, `ITUNESOWNER`, and `ITUNESPURCHASEDATE`. You can leave these commented-out codes alone if you do not want to attach your personal information to your songs.

`ITUNESACCOUNT` - Your Email Address
<br>
`ITUNESOWNER` - Your Name
<br>
`ITUNESPURCHASEDATE` - Date of Purchase (Year-Month-Day Hour:Minute:Second)

## Questions About the Web Sources Scripts
#### Q: How do I change the purchasing country?
A: The default purchasing country is the United States. To change the default purchasing country, you will have to go to the .inc file and search for the line that has `ITUNESCOUNTRYID` in it. Below this line, you will see 143441, which is the iTunes storefront ID of the United States. You can change this storefront ID to the storefront ID of the country you want it to be, and you can find these storefront IDs of different countries at this [link](https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/Information/iTunes%20Country%20Codes%20and%20Storefront%20IDs.csv) and this [link](https://gist.github.com/hmml/8942940).

*Example Using Germany as the Purchasing Country:* <br>
```
OutputTo "ITUNESCOUNTRYID"
Say "143443"
Say "|"
```

#### Q: How do I get a genre ID that is not listed in the web sources scripts?
A: Some of the most common genre IDs are already accounted for in these web sources scripts. However, if there is a genre ID that is not listed in web sources scripts, you can add that genre ID in the .inc file by searching for the line that says `ITUNESGENREID` and following the same format as the other genre IDs. To find more genre IDs, you can click on this [link](https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/Information/iTunes%20Genre%20IDs.csv).

#### Q: How do I get music metadata from a country of Apple Music or iTunes Store that is not available in the repository?
A: You will have to go to the .src file and change the country code in it. To find country codes, you can click on this [link](https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/Information/iTunes%20Country%20Codes%20and%20Storefront%20IDs.csv) or this [link](https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/Information/iTunes%20Country%20Codes.md).

*Example Using Germany as the Country Code:* <br>
```
[IndexUrl]=https://itunes.apple.com/search?media=music&entity=album&limit=200&country=de&lang=en_us
```

## Additional Information
* To find more web sources scripts for Mp3tag, click on this [link](https://community.mp3tag.de/c/development/web-sources-scripts/12)
* To learn more about how to use web sources scripts in Mp3tag, click on this [link](https://github.com/jonaaa20/itunes-web-sources)
* To learn more about the APIs, [click here for the Apple Music API](https://developer.apple.com/documentation/applemusicapi/) and [click here for the iTunes Store API](https://affiliate.itunes.apple.com/resources/documentation/itunes-store-web-service-search-api/)
* To learn more about the syntax of these web sources scripts for Mp3tag, click on this [link](https://help.mp3tag.de/main_online.html)
* To learn more about the tag fields in Mp3tag, click on this [link](https://help.mp3tag.de/main_tags.html)

## License
[MIT](https://github.com/MrBukLau/mp3tag-web-sources-scripts/blob/main/LICENSE)
