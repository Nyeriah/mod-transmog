# Transmog Module

> [!WARNING]  
> If you used the old-subscription system for TransmogPlus option before this [commit](https://github.com/azerothcore/mod-transmog/commit/8237df6f88d40d1d83a6f11b86a7187f99f57c99), please update your mod-transmog module to the latest revision and also download the new module [mod-acore-subscriptions](https://github.com/azerothcore/mod-acore-subscriptions).

- Latest Transmog build status with azerothcore: [![Build Status](https://github.com/azerothcore/mod-transmog/actions/workflows/core_build.yml/badge.svg)](https://github.com/azerothcore/mod-transmog/actions)

This is a module for [AzerothCore](http://www.azerothcore.org) that adds **Transmog**rification feature, it's based on [Rochet2 Transmog Script](http://rochet2.github.io/Transmogrification.html) 

## Important notes

You have to use at least this AzerothCore commit:

<https://github.com/azerothcore/azerothcore-wotlk/commit/b6cb9247ba96a862ee274c0765004e6d2e66e9e4>

If using this module with an AzerothCore commit older than

<https://github.com/azerothcore/azerothcore-wotlk/commit/b34bc28e5b02514fca3519beac420c58faa89cad>

please delete the IDs 50000 and 50001 from npc_text before upgrading AzerothCore:
```sql
DELETE FROM `npc_text` WHERE `ID` IN (50000,50001);
```
Otherwise there will be conflicts for these IDs. The module will now use IDs 601083 and 601084 as default.

## Requirements

Transmogrification module currently requires:

AzerothCore v1.0.2+

## How to install

### 1) Simply place the module under the `modules` folder of your AzerothCore source folder.

You can do clone it via git under the azerothcore/modules directory:

```sh
cd path/to/azerothcore/modules
git clone https://github.com/azerothcore/mod-transmog.git
```

or you can manually [download the module](https://github.com/azerothcore/mod-transmog/archive/master.zip), unzip the Transmog folder and place it under the `azerothcore/modules` directory.

### 2) Import the SQL to the right Database (auth, world or characters)

Import the SQL manually to the right Database (auth, world or characters) or with the `db_assembler.sh` (if `include.sh` provided).

### 3) Re-run cmake and launch a clean build of AzerothCore

### 4) Place transmog npc

With a gm account goto the location you want to add the npc and use this command:

```
.npc add 190010
```

**That's it.**

### (Optional) Edit module configuration

If you need to change the module configuration, go to your server configuration folder (e.g. **etc**), copy `transmog.conf.dist` to `transmog.conf` and edit it as you prefer.


## License

This module is released under the [GNU AGPL license](https://github.com/azerothcore/mod-transmog/blob/master/LICENSE).





