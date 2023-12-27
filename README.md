<h1>Warning</h1>

Galactic-Contention-Layer-Scrape

Galactic Contention layer scrape in JSON format. This JSON will allow the 3rd party plugin SquadJS to be able to read the map and layer names of the mod of Galactic Contention.

This read me is in regard to SquadJS configuration. If you are not using SquadJS + Galactic Contention. You can ignore this project and files.

---
<br>

<h3>How does it work?</h3>

This file was added to help SquadJS bot to fetch the proper information about the Galactic Contention Level/Layers/Teams/Subfactions. To adhere a better environment and uniformity with SquadJS, we've created a JSON file containing all the necessary data. We will maintain this JSON file whenever we do modifications and/or update Galactic Contention.

_This our duty as Galactic Contention developers to maintain this json with our internal data scrapper via our editor widget_

_______
<br>

<h3>What to do?</h3>

If you do not have SquadJS. We strongly recommend you to setup SquadJS for monitoring purposes. It can be found here: " https://github.com/Team-Silver-Sphere/SquadJS "

1. Either copy the "Layers.js" file from the folder or copy the content of it.
2. Put it inside your SquadJS squad-server/layers configuration folder located in " $Path/$SquadJSfolder/squad-server/layers/layers.js ". You must replace the file " layers.js "
3. Save and relaunch SquadJS to validate everything is okay
4. Upon playing a Galactic Contention layer, the Squad JS bot will show the proper Galatic Contention layer name in Discord in the status bar.

_______
<br>

<h3>Okay but how does it work?</h3>

Our json is being scrapped by Galactic Contention developers via unreal engine. Sadly for unknown obnoxious reasons, the javascript "axios" GET request of SquadJS is not making the cut. It won't load or show the proper level/layers names on the discord SquadJS bot.

However, if we make a JS axios POST request with our mod ID as the setting, it works very well. (SUBJECT TO CHANGE SINCE WE ARE TRYING DIFFERENT THINGS)

If you look the difference between the original SquadJS layers.js file and ours, we are doing a POST request on the Galactic Contention workshop id.

```
    Logger.verbose('Layers', 1, 'Pulling layers...');
    const response = await axios.post( // Change get to post for mod support
      'http://hub.afocommunity.com/api/layers.json', [2428425228]
    );
```
