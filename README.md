# Judo score board

A full Judo scoreboard software in a *single HTML file*.
Usable without webserver, just open score.html locally in your webbrowser. The ressource folder is for convenience only.

![screenshot](screenshot.jpg?raw=true "Example view")

## HW-setup
The software was designed to operate in "duplicate-screen"-setup, so that the operator sees the same as the audience. 

## Configuration
On first start or by navigating to the setting menu (gear icon in bottom-left corner), the configuration dialogue is opened.

## Operating
A brief usage description is included in the menu. Points are assigned via mouse control, but there are also various shortcuts to control clocks, etc.

## Google Sheets configuration
To get data off a sheet you have to do following steps.

1. Copy [this Google Sheet template](https://docs.google.com/spreadsheets/d/1hddz-5w_Wb4MR8uZh4Q7mzHyleLJMmjpHnPbzbc-nzU/edit?usp=sharing), or create your own. It has to have following Columns to have all features. Other Columns can be added but don't have any impact on the scoreboard.

| Header | Info | Example |
| ----------- | ----------- | ----------- |
| whitename | Name of white fighter | Pinkman Jessy |
| redname | Name of blue figther | White Walter |
| done | Checkbox or true/false, mark if fight is done/over | true |
| groupname | Name of group | MU +100 kg |
| roundname | Name of round | Semi-Final |

2. Make sure your Sheet is set to share with "anyone with link".

3. get your spreadsheet-ID from the URL and your sheetname and set the variables whithin score.html:

``` js
        // set spreadSheetId and sheet variable, if you want to load fighter names from a Google sheet.
        var spreadSheetId = "";
        var sheet = "";
        var apiKey = ""; // optional
        var fightInfoJsonServerUrl = "";
```
I highly suggest you use a Google Developer API key. For more information visit [GSX2JSON](https://gsx2json.com/).

## GSX2JSON
This project currently relies on the use of GSX2JSON. It's an easy to use api, that fetches Google Sheet data and presents it as json.

As the developer Nick Moreton on his product page writes:

> Please do not use this hosted version for anything important. I am not able to quickly react if Google updates their API, or if the Heroku app crashes. If you want to use this for something important, I suggest Self Hosting.

For more information head over to [GSX2JSON](https://gsx2json.com/).

## Own bell / horn / audio samples
Own audio files can be added in base64 embedded form <audio id="sound[n]" src="data:audio/ogg;base64,...>

## Licence
Free usage and modification for non-commercial use. 
(c) 2019 https://github.com/tuxmike/
