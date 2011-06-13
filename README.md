#DnD Powers
## Dungeons and Dragons 4th Edition Power card helper for mobile devices

The purpose of this software is to provide a small interface to display character power
cards on mobile touch systems like iOS or Android. It allows to display "At-Will", "Encounter"
and "Daily" powers as a convenient list which allows toggling of further content as well as marking
powers as "used" via a simple right swipe (and unmarking them again via a left swipe).

This small app does not required anything but a very simple web server which is capable
of serving files (No PHP, Ruby, Python, etc. required). Just copy all files to a folder
which is served by a webserver and direct your browser to the uri of the index.html

Character File
--------------
The character is stored in a single json file `./character.json`

The file hols a simple object structure which places powers in the different categories

    {
      "at_will": [],
      "encounter": [],
      "daily": []
    }
    
Each categories represents an array of cards which themselves are also represented as json objects with pre-defined keys
which hold information about the character.
<dl>
    <dt>name<sup>*</sup></dt><dd>Name of the power</dd>
    <dt>level<sup>*</sup></dt><dd>Power level</dd>
    <dt>summary<sup>*</sup></dt><dd>Short power summary</dd>
    <dt>keywords<sup>*</sup></dt><dd>Array holding the multiple power keywords</dd>
    <dt>action<sup>*</sup></dt><dd>The power action type (Standard, Minor, Free)</dd>
    <dt>type<sup>*</sup></dt><dd>Type of the attack (Meelee, Range, etc.)</dd>
    <dt>target</dt><dd>Target of the power</dd>
    <dt>attack</dt><dd>Attack attributes (x vs. y)</dd>
    <dt>trigger</dt><dd>Power trigger</dd>
    <dt>hit</dt><dd>What happens on a hit</dd>
    <dt>miss</dt><dd>What happens on a miss</dd>
    <dt>effect</dt><dd>Power effect</dd>
    <dt>special</dt><dd>Special notes (Typically noted on the power cards)</dd>
    <dt>subnote</dt><dd>A subnote (Like Does xy on Level 11)</dd>
</dl>

<small>Entries marked with <sup>*</sup> are required</small>

So an example might look like this

    { "name":     "Sacred Flame",
      "level":    "Cleric Attack 1",
      "summary":  "Sacred light shines from above, searing a single enemy with its radiance while at the same time aiding an ally with its beneficent power.",
      "keywords": ["Divine", "Implement", "Radiant"],
      "action":   "Standard Action",
      "type":     "Ranged 5",
      "target":   "One Creature",
      "attack":   "Wisdom vs. Reflex",
      "hit":      "1d6 + Wisdom modifier radiant damage, and one ally you can see chooses either to gain temporary hit points equal to your Charisma modifier + one-half your level or to make a saving throw.",
      "subnote":  "Increase damage to 2d6 + Wisdom modifier at 21st level."
    }
    
A full example character (My cleric "Belgretor Tamiklos") can be found in `./example_character.json`

- - -

Dungeons and Dragons and all content associated with it is (C) 1974 - 2011 Wizards of the Coast

the DnDPowers application does not hold any rights to the content
and so does not provide the material associated with Dungeons and Dragons
You will have to fill data in yourself