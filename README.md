This is a rudimentary mining robot script for ComputerCraft.

Install
-------

- Place down a disk drive with a floppy disk in it and if necessary, a computer to access it
- Place all the Lua files on the disk
- Edit the config file (explanation below) to correctly identify all locations
- Place a turtle next to the disk drive, make sure the wireless modem is not on the side touching the drive
- All the necessary files should be now on the turtle. Simply run "bot" to start

Configuration
-------------

You need to edit the botconfig file to set up the bot's navigation system and mining and drop point waypoints.

- Set "facing" to the direction where the bot is facing when it's started
- Set startX, startY and startZ to the coordinates where the bot is placed
- Set mineX, mineY and mineZ to the coordinates where the bot should move before it starts mining
- Set dropX, dropY and dropZ to the coordinates where the bot should return to drop off whatever it mined
- Set dropFacing to the direction the bot should face when dropping off mined blocks
- Set safeHeight to the maximum height where you want the bot to mine. Useful if you want to prevent it from destroying buildings or such
- Optional: masterId can be set to an ID of a computer where the bot should send log messages via rednet

Note: The drop position should be a point **next to** a transposer or such which can pick up the dropped items.

Implementation details
----------------------

The bot has a navigation system based on the A* algorithm. It should be capable of navigating around obstacles, players or mobs in order to reach any of the needed waypoints. 

The mining code is currently quite straightforward: It will dig a rectangular 2-high area until full, after which it will return to the drop point, unload, and go back to the mining point.


