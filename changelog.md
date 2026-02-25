# Changelog: 25.02.2026 [Release 3.0.0]

> **⚠️ Note:** If you are upgrading from an older version, please update your message configurations to the MiniMessage format, as Legacy Colors are no longer supported. Failure to do so will result in your messages appearing without colors.
> If something doesn't work as expected, please report the error on [Discord](https://discord.com/invite/Ty7JUbz8Cv) or [GitHub Issues](https://github.com/ItQerk/BackpackPlus-Issues/issues).



> **⚠️ Warning:** Before proceeding with this update:
> 1. Backup the `BackpackPlus` folder to avoid losing custom configurations or data.
> 2. If you are using a MySQL database, ensure it is backed up to prevent any potential data loss.


## Key Changes
- **Main:**
  - **Spigot servers** are no longer supported.
  - **Paper API** has been implemented instead of Spigot API.
  - **Legacy Colors** are no longer supported; please update them to the `MiniMessage` format. You can use the default files as a template.
  - All messages now support the **MiniMessage** format.
  - The plugin now supports versions **1.20 and newer**.

- **Added:**
  - Added a check to verify if the server software is supported (**Folia / Paper / Paper forks**).
  - Added pagination for the GUI showing all players' backpacks.
  - Added the ability to set a default placeholder for `<backpack_owner>`:
    - ```yml
      backpack-placeholders-defaults: 
        backpack-owner-name: "<#1cc2f6><player>"
  - Added new NBT tags for backpacks:
    - Backpack Owner UUID
    - Backpack Owner Name
  - Added a template for backpack lore content (colors and formatting can now be customized):
    - ```yml
      # Default values for backpack placeholders
      backpack-placeholders-defaults:
        #... other
        # <amount> = amount of specific item
        # <name> = material or custom item name
        content-lore-template: "<#f9c100><amount>x <#dadada><name>"
  - You can now customize virtually all messages.
  - Added a custom logging system for testing purposes.
  - Added the `/backpack recipes` command (`backpackplus.view.recipes`), which displays all craftable backpacks.
  - Added a new config option to prevent opening a backpack when right-clicking a chest or similar block; the block will be opened instead. This also applies to doors and trapdoors: `block-interaction-blocks-prevent-backpack-open`.
  - Added support for `Folia`.
  - Added an option to hide tooltips for GUI elements.
  - Added the remove-inactive-backpacks option, which removes inactive backpacks after a specified number of days.
  - Added support for these plugins:
    - DeluxeCombat
    - PvPManager
  - Added an option to enable or disable the ability to use backpacks during combat (if you have one of the supported plugins installed). Option: `allow-open-backpacks-in-combat: false`
  - Added `cannot-use-in-combat` message to language files
- **Removed:**
  - Removed saving the backpack tier and size within the content.
  - GUI buttons will no longer be saved in the content.
- **Fixed:**
  - All players' backpacks are no longer loaded when the plugin starts.
  - Fixed saving backpacks during plugin shutdown (the plugin will now wait for the save to finish).
  - Saving all backpacks is now performed with a single query instead of separate queries.
  - Fixed the function for checking if a String is valid Base64; it no longer incorrectly detects materials as Base64.
- **Database**
  - Improved the database code.
  - Overhauled the entire database system for significantly faster performance.
  - Added a `tier` column for backpacks in the database (backpacks will automatically update in the database).
---

### Upgrade Steps
1. Backup the necessary files and database as described above.
2. Replace the existing plugin files with the new version.
3. Update `config.yml` according to the latest format.
4. Update your language file to the `MiniMessage` format.
5. Restart the server and verify that everything is functioning correctly.
---
