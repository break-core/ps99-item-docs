# PS99 Item Documentation
Docs for how items are layed out in the Economy Bucket.

## Format
Items in the Economy Bucket (simply called Bucket) are stored in a JSON format. This makes it easy to read. The format looks like this:
```json
[
    "Item Type",
    {
      "id": "Item Name"
    },
    2528.24
]
```

"Item Type" represents the type of the item. The main types include:
- `"Pet"`, a type that represents every Pet ever.
- `"Misc"`, a type that represents miscellaneous items which does NOT include:
  - Potions (like Lucky Potion or Coins Potion)
  - Enchants (like Criticals or Party Time)
  - Fruits (like Candycanes or Apples)
  - Eggs (like Exclusive Egg 19 or Huge Machine Egg 1)
  - Hoverboards (like Banana Hoverboard or Doodle Hoverboard)
  - Charms (like XP Charm or Glittering Charm)
  - Booths (like M-10 Booth or Corgi Booth)
  - Seeds (like Coin Seed or Diamond Seed)
  - Lootboxes (like X-Large Christmas Present or 2024 New Years Gift)
  - Boxes (like Small Box)

The number at the very end is the value of the item in RAP (Recent Average Price). All RAP values are stored with decimal values included, so if you are displaying these values in an application you should trim the decimal numbers off by using a number rounder.
 
## Item Keys
Different items have different "keys" (parameters, but in JSON). Let's go over what keys exist

### Pet Keys
Pets have specific keys to them that define properties of them. These include the `"pt"` and `"sh"` keys.

`"pt"` defines the "Pet Tier", or the tier of the pet. Two numbers are used to represent the value. `1` is used to represent Golden Pets, and `2` is used to represent Rainbow Pets.
`"sh"` defines if a Pet is "Shiny", defined by a `true` value.

> [!NOTE]
> For pets that don't have the `"sh"` key, it means they aren't shiny. The same goes for pets that don't have the `"pt"` key. It means they will not have a pet tier.

### Potion Keys
Potions have a key that defines what tier it is, in the form of a number. This key is called the `"tn"` (Tier Number) key. Potions will ALWAYS have the `"tn"` key. The value of `"tn"` starts from 1 (indicating tier 1), and go up to the maximum tier number.

### Enchant Keys
Enchants use the exact same key format as Potions do. That being, they have a key called `"tn"` that indicates the tier number of the enchant that starts at 1 (indicating tier 1) and goes up to the maximum number for enchants.

> [!NOTE]
> Special enchants, like "Fireworks" or "Tap Teamwork" always use a tier number of 1.

### Charm Keys
Charms use the same key as Potions and Enchants do (`"tn"`). However, the value for all charms is ALWAYS 1, because this value defines the base tier of the charms.

### Notes on Formatting
All miscellaneous items use their full names. If you're looking for a miscellaneous item, use it's full name.
For anything else, keep note of the naming scheme. Not everything uses the in-game name! For example, the "Lucky Eggs" potion is just called the "Lucky" potion inside of the data.
