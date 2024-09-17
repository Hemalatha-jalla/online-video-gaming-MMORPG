Online Video Gaming Database
This repository contains SQL scripts for creating and managing a database for an Online Video Gaming system. The database includes tables for managing user accounts, game regions, items, creeps, player characters, and their interactions.

Table of Contents
Database Overview
Entities Overview
Independent Entities
Dependent Entities
Database Setup Instructions
File Structure
Sample Data
Database Overview
The Online Video Gaming database consists of the following tables:

Account - Stores user account information.
Region - Details about various game regions.
Item - Information on items available in the game.
Creep - Details on different enemy creatures.
PlayerCharacter - Information about characters created by players.
ItemInstantiation - Records of items assigned to characters.
CreepInstantiation - Records of creeps encountered by characters.
Entities Overview
Independent Entities
Account Table

Attributes:
AcctName (VARCHAR): Primary Key, unique account name.
Password (VARCHAR): User's password.
LastSignedOn (DATE): Last date the user signed in.
SbscrbrName (VARCHAR): Subscriber's name.
SbscrbrAddress (VARCHAR): Subscriber's address.
SbscrbrEmail (VARCHAR): Subscriber's email address.
SbscrbrPhone (VARCHAR): Subscriber's phone number.
AcctCreatedOn (DATE): Account creation date.
Description: The Account table holds user credentials and personal information.
Region Table

Attributes:
RegionName (VARCHAR): Primary Key, name of the region.
Climate (VARCHAR): Climate type of the region.
Precipitation (VARCHAR): Precipitation level in the region.
Foliage (VARCHAR): Type of vegetation in the region.
Description: The Region table contains details about different game regions.
Item Table

Attributes:
ItemName (VARCHAR): Primary Key, name of the item.
ItemType (VARCHAR): Type of the item (e.g., Weapon, Consumable).
ItemDamage (INT): Damage value of the item, if applicable.
Description: The Item table lists items available in the game, including weapons and accessories.
Creep Table

Attributes:
CreepName (VARCHAR): Primary Key, name of the creep.
HitPoints (INT): Health points of the creep.
Mana (INT): Mana points of the creep.
Attack (INT): Attack power of the creep.
Description: The Creep table describes various enemy creatures in the game.
PlayerCharacter Table

Attributes:
CharName (VARCHAR): Primary Key, character name.
Level (INT): Level of the character.
ExpPoints (INT): Experience points of the character.
Type (VARCHAR): Type of character (e.g., Warrior, Mage).
MaxHitPoints (INT): Maximum hit points.
MaxMana (INT): Maximum mana points.
CurrHitPoints (INT): Current hit points.
CurrMana (INT): Current mana points.
LastPlayed (DATE): Last date the character was played.
CreatedOn (DATE): Character creation date.
AcctName (VARCHAR): Foreign Key, links to Account table.
Description: The PlayerCharacter table contains information about characters created by players.
Dependent Entities
ItemInstantiation Table

Attributes:
IDNum (INT): Primary Key, unique identifier for the item instance.
Modifier (VARCHAR): Modifier applied to the item (e.g., Fire Enchantment).
WhenCreated (DATE): Date the item was instantiated.
CharName (VARCHAR): Foreign Key, links to PlayerCharacter table.
ItemName (VARCHAR): Foreign Key, links to Item table.
Dependencies: The ItemInstantiation table depends on the PlayerCharacter and Item tables, linking items to specific characters.
CreepInstantiation Table

Attributes:
IDNum (INT): Primary Key, unique identifier for the creep instance.
CharName (VARCHAR): Foreign Key, links to PlayerCharacter table.
CreepName (VARCHAR): Foreign Key, links to Creep table.
Dependencies: The CreepInstantiation table depends on the PlayerCharacter and Creep tables, recording which creeps are encountered by which characters.
