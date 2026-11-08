# Not Assign: army collections

Model collections for the **Not Assign** table in Tabletop Simulator. Paste a Yellowscribe code, press **BUILD ARMY**, and the army lands on the table with real models. No picking models by hand.

Every file in [`armies/`](armies) is one army's models, labelled so the table knows which model is which. A collection is made by someone who plays that army. The table downloads collections from this repository whenever it builds an army, so once a pull request is merged, everyone has the new or fixed army. No table update is needed.

## Playing

1. Subscribe to [Not Assign in the Steam Workshop](https://steamcommunity.com/sharedfiles/filedetails/?id=3833082699) and load it in Tabletop Simulator.
2. Build your list in [New Recruit](https://www.newrecruit.eu) and export it for Tabletop Simulator (Yellowscribe). You get a short code.
3. In TTS, paste the code into the **Auto Army** panel and press **BUILD ARMY**.

- **Army: auto-detect** picks the collection for your roster's faction. Click the button to choose a collection yourself.
- Allied units (for example an Imperial Knight in a Sororitas list) come from their own faction's collection.
- The chat lists anything that didn't match exactly: `[fallback]` and `[closest]` are stand-ins, and `[no model]` means the collection has nothing for that model, so it's skipped.

## Model credits

The models in these collections were made by people from the Tabletop Simulator community: photoscans, kitbashes, recolours and models ripped from *Warhammer 40,000: Gladius*. Not Assign only sorts them into armies. Thank you to:

| Author | Work | Armies | Models |
|---|---|---|---|
| **Raikoh** (ForceOrg) | photoscans, Gladius rips, kitbashes | Adepta Sororitas, Adeptus Custodes, Drukhari, Imperial Knights | 214 |
| **Seaborne** | photoscans, kitbashes | Adepta Sororitas, Adeptus Custodes, Adeptus Mechanicus, Drukhari, Imperial Knights | 132 |
| **Savage Boii** (40k Translator) | original models, photoscans | Adepta Sororitas, Adeptus Custodes, Adeptus Mechanicus, Drukhari, Imperial Knights | 53 |
| **Orange Blue Hue** | models | Drukhari | 50 |
| **Clostry** (Clostry's Figure Corner) | models | Adeptus Custodes, Adeptus Mechanicus | 28 |
| **Vicmo & Knuckles Workshop** | Gladius rips, rescaled models and fixed colliders | Adeptus Mechanicus | 20 |
| **Mothman Zack** | models | Adeptus Mechanicus | 17 |
| **Dark Trinity** | models | Adeptus Mechanicus | 17 |
| **SirDragdord** | recolours, edits | Adeptus Mechanicus, Drukhari | 14 |
| **Slambo Minis** | models | Adepta Sororitas | 13 |
| **Lone_Wolf_28** | models | Adepta Sororitas | 8 |
| **Den of Imagination** | models | Adeptus Custodes, Imperial Knights | 5 |
| **Colonel Cabbage** | models | Drukhari | 3 |
| **Retipupu** | kitbash | Drukhari | 1 |
| **Galling** | kitbash | Drukhari | 1 |
| **ZenphyL** | model | Drukhari | 1 |
| **Ziggy Stardust** | photoscan | Imperial Knights | 1 |

*Models* counts the models in these collections that credit the author; a model can credit more than one. Each model's own credit is in its description in the collection file (`# By …`). Two Adeptus Mechanicus models, *Sicarian Ruststalker* and *Sicarian Ruststalker Princeps*, have an unknown author: if they're yours, tell us.

The models belong to their authors. If you made one of them and want the credit changed or the model removed, contact us (Discord below) and it will be done.

## Adding or improving a collection

You need your painted or downloaded models in TTS and a free GitHub account. No coding.

1. **Bag your models.** In TTS, put every model of the army into one bag. Then right-click the bag and choose **Save Object**. The file is saved to
   `Documents\My Games\Tabletop Simulator\Saves\Saved Objects`.
2. **Label them.** Open that file on [40k.notchu.dev](https://40k.notchu.dev) and pick the army. For each model, choose what it is and tick what it holds: weapons and wargear such as *Sacred Banner*. The site gets units and weapons from [BSData](https://github.com/BSData/wh40k-11e), so names match your roster.
3. **Send it.** Press **Submit to catalog**. The site downloads `<army>--<your-name>.json` and opens this repository's upload page. Drag the file there, then press **Propose changes** and **Create pull request**.

The file name sets the army's name on the table: `imperial-knights--bob.json` shows up as *Imperial Knights*. Use the faction's name as BSData spells it, so allies and auto-detect can find it.

To fix an existing collection, open its file from `armies/` on the site, change it, and send it the same way under the same file name.

### What makes a good collection

- **One model per loadout is enough.** The table copies models, so one Battle Sister with a meltagun covers every meltagun sister. Several sculpts of the same loadout are picked at random for variety.
- **Tick only what you can see on the model.** Leave standard gear unticked (bolt pistol, close combat weapon). A model with nothing ticked fits any loadout of its name.
- **Mark a `fallback`** (under *More rules*) for each model type. It's used when no exact loadout exists, so the unit is never empty.
- **One paint scheme per collection**, or tag schemes with *paint scheme* so a unit never mixes them.
- **Credit the models.** For every model, write who made it in *More rules* → *Comments* (it's saved as `# By <author>`), and say whose models you used in the pull request. We'll remove anything an author asks us to.
- **Check the Missing tab.** It lists the army's models that have no model in your collection yet.

### Review

A pull request is merged when the file:
- is a single bag exported by the site, with the army and faction filled in;
- loads in TTS and its models come from public URLs (Steam Workshop and so on);
- has sensible labels, checked by building a test army with it.

## File format

Each file is a normal TTS saved object: one bag tagged `AutoArmy`, so you can also load it in TTS from Saved Objects. The bag's `GMNotes` hold `{"autoArmy":1, "army", "author", "faction", "bsdata", "updated"}`. Each model's **Name** is its name in the roster without the loadout part (`Battle Sister`, not `Battle Sister w/ Special Weapon`). Its **Description** has one line per item it holds, plus optional `fallback`, `alias: <name>`, `unit: <unit>`, `variant: <scheme>` and `# comment` lines.

## MY Discord: as_notchu