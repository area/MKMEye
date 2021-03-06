# MKMEYE 0.1b

Sell on MKM/MagicKartenMarkt (or MCM for international folks -> https://www.magiccardmarket.com) by scanning your cards with image recognition.

This software allows you to identify cards by image recognition, match them to the MKM stock and directly sell them on the marketplace, making adding bulk cards to MKM as easy as possible.

[![MKMEye Video](https://www.alexander-pick.com/github/screen.JPG)](https://www.youtube.com/watch?v=JfRXl8Rf47I "MKMEye Video")

#### Quick Start downloads

Here are some working binaries and the needed assets for your enjoyment. These are not updated with every push so this version might be a bit outdated towards the real source version:

- [MKMEye 01.b](https://www.alexander-pick.com/github/MKMEye-01b-Release_11042017.rar)
- [ImageDBCreator](https://www.alexander-pick.com/github/ImageDBCreator-01b-Release_11042017.rar)
- [Needed Assets](https://www.alexander-pick.com/github/Assets_11042017.rar)

#### The GUI has 3 Hokeys

Q - check the cam identified card against the mkm database, the mkm match will be shown in the top right corner
W - If the identified card is not yours or a reprint of the target, use this key to iterate through the possible matches
S - Put the card on MKM for sale, the card will be listed on MKM directly

I am using MKMEye regulary at the moment and it works very well for me. I hope you enjoy this software as much as I do.

### But Why?

If I feel lucky and buy a collection to merge into mine I usally end up with a lot of bulk. You know these cards not really worth much. But selling it usally is a lot of work since you have to add each card and ship it. So why not skipping at least one of the parts if its possible? This is how this project started. I was searching the web upside down for a good solution and found quite a few image recognition projects, but they were all very basic at this point. I found this rather old project public domain project by Peter Sterm realeased on reddit. It was written in C# using AForge for image detection and had the needed basics for my idea. This is how this started, based on the original Magic Vision this pretty advanced project developed, I have to say I am a little bit pround of it. 

At the moment my personal goal is to sell that much Bulk that way so that I can get some nice graded Antiquities or other vintage cards for my collection.

### How to get it working

#### Prerequisites 

1.) First you need a MySQL Server, set one up:

https://dev.mysql.com/downloads/mysql/

2.) Install the .NET MySQL Conenctor 6.9.9 (included in /Assets) or download it here:

https://dev.mysql.com/downloads/connector/net/6.9.html

2.) Create a database and add the "cards" table structure (included in /Assets)

3.) Get the CCGHQ XLHQ MTG Images (around 13 Gb + the newer set singles CCGHQ) 

4.) Compile or download the ImageDBCreator and edit the config to match your MySQL DB.

5.) Run the ImageDBCreator to build the pHash DB from the images. Point it to the extracted XLHQ images (or other source) and let it run, this might take a while.

#### Running MKMEye

1.) Compile or download the MKMEye

2.) Change the config and add your MKM Api Key + MySQL Details

3.) Start scanning and selling

**Supporters can request a copy of my personal pHash DB, just leave me a message.

### Some Notes

- I tried to only match the art and the full card image. From various tests I decided to go with matching the full card, it works pretty well.
- If you need a tool to crop art from images anyways, i.e. the widly known xlhq images, it is included in this repo too. For the process is has not much use anymore.
- Tool adds articles with MKM AVG prices, if you are luck, this works very well with the price update of my MKMTool project which could be found here: https://github.com/alexander-pick/MKMTool
- Creating the MySQL DB might take an hour or two. Don't be afraid if the tool is not responding, I didn't pay much attention to make it fancy task supported, but it will work.
- Watch what you add to mkm, don't blame me if you add something twice or somethign wrong - this tool does not replace a brain.

### Support & Donations

The development of this tool cost me a lot of time recently but it was worth it to see it done now. If you like this tool or you are a LGS/Powerseller which wants to use it everyday, please consider a donation.

You can bye me something of my amazon wishlist here:

https://www.amazon.de/registry/wishlist/PY25W6O71YIV/ref=cm_sw_em_r_mt_ws__ugkRybY0HFNYD

**If you are producing a commercial product and need some help with the MKM API or you want to integrate some of my code in your application, feel free to contact me.**

### And finally some more links

Original Magic Vision Release:
https://www.reddit.com/r/magicTCG/comments/lccrx/full_source_code_of_the_mtg_card_image/

Source for the JSON used by the scraper to get the multiverseid needed for the gatherer image download:
https://mtgjson.com/
