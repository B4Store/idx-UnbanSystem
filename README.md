# Ban List Script
- This script allows server admins with `god` permissions to view and unban players who are currently banned from the server. It utilizes `qb-menu` to display a list of banned players and allows admins to remove bans directly from the menu.

# Features
- View Ban List: Admins with `god` permissions can open a list of all currently banned players.
- Unban Players: Admins can select a banned player from the list to remove their ban.
- Database Integration: The script uses a MySQL table `bans` to store ban information, such as player name, license, and reason for the ban.

# Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-menu](https://github.com/qbcore-framework/qb-menu)

# Preview
![Config Preview](https://r2.fivemanage.com/9sDcJPkZq3Zy9nUxeQvk9/images/Config.png)
![Command Preview](https://r2.fivemanage.com/9sDcJPkZq3Zy9nUxeQvk9/images/Command.png)
![Menu Preview](https://r2.fivemanage.com/9sDcJPkZq3Zy9nUxeQvk9/images/Menu.png)

# Commands
- `/banlists`: This command opens the ban list for players with the `god` permission. Only those with the required permission can access and interact with the ban list.

# Installation
- Buy From [Tebex](https://b4-store.tebex.io/package/6448802) For Free
- Ensure you have the `qb-core` framework installed on your server.

# Add the bans table to your MySQL database:
```sql
CREATE TABLE `bans` (
    `id` INT(11) NOT NULL AUTO_INCREMENT,
    `name` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `license` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `discord` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `ip` VARCHAR(50) NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `reason` TEXT NULL DEFAULT NULL COLLATE 'utf8mb4_general_ci',
    `expire` INT(11) NULL DEFAULT NULL,
    `bannedby` VARCHAR(255) NOT NULL DEFAULT 'LeBanhammer' COLLATE 'utf8mb4_general_ci',
    PRIMARY KEY (`id`) USING BTREE,
    INDEX `license` (`license`) USING BTREE,
    INDEX `discord` (`discord`) USING BTREE,
    INDEX `ip` (`ip`) USING BTREE
) COLLATE='utf8mb4_general_ci' ENGINE=InnoDB;
```

- Place the script files in the appropriate resource folder and start the resource in your server configuration.
- Ensure that your players with the `god` role have the correct permissions set up in `qb-core`.

# Usage
- Type `/banlists` in the chat to open the ban list.
- Select a player from the menu to remove their ban.

# Permissions
- This script uses `QBCore.Commands.Add` to ensure that only players with the `god` permission can execute the `/banlists` command. If a player without the required permission tries to use the command, they will be notified that they do not have access.

# Notes
- The script will only show bans that are still active (not expired).
- The script is designed to be secure, ensuring only authorized admins can manage bans.

# All Rights For [ B4Store / i.dx ]
- For Support `->` https://discord.gg/b4s
