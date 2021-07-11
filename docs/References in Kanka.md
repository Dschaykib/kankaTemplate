# References in Kanka

In Lanka you can create different kinds of entities like characters, locations or events. Each one of these can hold a lot of information and is quite useful in their own way. But to get the most out of it, you should mention, reference to or just link your entities within each other. 

> The mighty hero **Bork**, who was on the hunt for **Orcs**, travelled to the town of **Fungha**. To his surprise the town was full of people who celebrated **Highharvestide**.

In this post I will show the different ways on how to relate and link entities together. To explain the different ways of referencing I will use the following:

- Borg Borgins (character)
- Orc (races)
- Fungha (location)
- Highharvestide (event)

All entities can be found and looked at in [this campagin](https://kanka.io/en/campaign/77331).



## Mentions

This will be probably the one you use the most. When you write a text and want to quickly mention another entity you can use the `@` sign. After typing at leat three letters, the autocompletion will kick in and make suggestions for entities. The `@Borg` is then changed internally to '[character:1944809]'. This is called the advanced mentioning. It uses the type of the entity (here a character) and its index id (here 1944809). This index can also be found in the browser's site address.

The displayed text will be the name of the mentioned entity. To change this text you can use a  `|` at the end of the mentioning and add a text to display: `[character:1944809|the mighty hero]`. This also works from the `@`sign as long as you are still within the marked area: `@Borg|the mighty hero`. 

There is also a known Firefox bug with the summer note editor, where you need to enter a new line to escape the marked area.

## Reference fields

Since Lanka 1.11, if you want to reference a specific field from an entity, you need a similar syntax to the display changing text. Let's say, that Borg has the title "the mighty hero". To reference his title, you can use `[character:1944809|field:Title]`.

## Reference attributes

You can reference an entity's attributes within its own description by using curly brackets. Assume Borg has his hit points (HP) and number of killed monsers (mosterkills) as attributes. With `{HP}` and `{monsterkills}` you can show the values of them in the text. 

Note: To get them setup correctly, you need to select them over the autocompletion, just using the curly brackets does not work. The curly brackets will get transformed into `{attribute:2203635}`, where the id of the attribute is unique and therefore case specific. This means when you delete and recreate the attribute it will receive a new id. Therefore these references will not work within templates.

## Links

Another form of reference can be achieved by using good old website links. In the editor there is the link option wich asks for a display text and a link. Here you could enter a direct link to another entity.

Note: To link to a specific note, you can open the note in a new tab to edit and then remove the `edit?from=main` part of the link.
https://kanka.io/en/campaign/77331/entities/1944809/entity_notes/88631/edit?from=main

-----

There are also other forms of connecting entities together.

## Connections

Formerly knows as relations, with connections you can create all kind of links between entities. For example you could show the connections within a family or organisation. Since Kanka 1.12, it is not only possible to show these connections in a nice graph but also show related entities and entities with mentions.

##Parent entities

Some entities can have a parent entity. An example would be town A to D are in region 1 and town E and F are in region 2. Both regions are in the same country Kankopia. Each of these entities is a location, where the region is the parent location of the towns and the country is the parent location of the regions.

Every entity type except these can have a parent entity:

- Characters
- Items
- Conversations (deprecated)
- Dice Rolls (deprecated)

## Unknown

If a reference is not possible because the target does not exist or you do not have the permisson the read them, the displayed text is `Unknown`.



