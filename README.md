> **notice:** discord explicity prohibits the use of unauthorized third-party scripts through their [TOS](https://discord.com/terms). so, usage of this script can result in consequences such as account suspension, bans, etc. Please use at your own risk. 

# [deletecord](https://bekkibau.github.io/deletecord) 

[github](https://github.com/bekkibau/deletecord) / [greasyfork](https://greasyfork.org/en/scripts/518587-deletcord-delete-all-messages-in-a-discord-channel-or-dm-mass-deletion)   
mass delete all discord messages from any dm or channel.  

fork of [undiscord](https://github.com/victornpb/undiscord)


# use
### prereq
download a userscripts manager (eg. [ViolentMonkey](https://violentmonkey.github.io))
### steps
1. download this script from [GreasyFork](https://greasyfork.org/en/scripts/518587-deletcord-delete-all-messages-in-a-discord-channel-or-dm-mass-deletion) or the JS file here
2. open [discord](https://discord.com/app) in the browser
3. enable script
4. open the dm or channel you want to delete
5. press the new `trash icon` in top right-hand corner
6. press all the blue `get` buttons in the popup
7. configure [options](#options) (default: all)
8. press green `start` button
9. ** "prevent automatically sleeping on power adapter" 
10. run a few more times to delete any skipped messages (quicker than first time) 
11. ** re-enable allowing computer to sleep
12. done! - you can disable the userscript until the next time you need it

** you only need to prevent sleep if you have a lot of messages to delete and/or will likely not be using your computer the whole time (ie. display turns off and computer sleeps) (instructions for [macOS](https://support.apple.com/en-ca/guide/mac-help/mchle41a6ccd/mac), please google for this setting for other OS) 

# options
self-explanatory. See original documentation if you need help, refer to the [wiki](https://github.com/bekkibau/deketecord/wiki).

find `message ids` by right-clicking them  
adjust `delay` in ms to test for optimal deletion rate 
- `Range`
    - `before date`
    - `after date`
    - `After message id`
    - `Before message id`  
- `Search Delay` rec: 1000
- `Delete Delay` rec: 800
- `Search messages`
    - `Containing Text`  
    - `Has: Link`
    - `Has: File`
    - `Include Pinned`

# tested
### default
![default popup](img/default.png)

### options selected
sample options for dm - here i pressed the `get` buttons, selected `date range` and adjusted the `delete delay` with `screenshot mode`

### starting...
this is what it looks like right after pressing `start`. total number of messages to delete (might be slightly inaccurate due to system messages)

![configured popup](img/config.png)

### while running (ratelimited)

when rate limited, might only delete 1-3 messages are between short delays. The script adjusts the delete api call delays according to  response (usually 0.5 - 2 ms) 
![screenshot ratelimited](img/ratelimited.png)

### while running for dms (not ratelimited)
when not being ratelimited, it goes pretty fast.
![screenshot not ratelimited](img/not_ratelimited.png)

### bug - miscalculating deleted percent
bug where percent deleted exceeds or below 100% -- i think it might be off by ~1000s of messages. you can see the datetime of the latest messages deleted and estimate how many are left since the beginning / end of your messaging history until this is fixed 
![bug deleted percentage](img/bug_100.png)

### bug - done
once all messages are found and deleted, the script will end automatically. I recommend you press `start` again to delete any messages it missed - not sure why this happens, but its only a small percent that get missed
![finished](img/done.png)

### bug - rerun
only few 100s of messages were found the 2nd time, idk im paranoid so, run it few more times just in case!
![rerun](img/rerun.png)

### 0 messagges left
after rerunning obsessively, it'll eventually get to 0. I recommend you skim through the entire chat to confirm.
![0 left](img/0.png)

# untested
I didn't test all the features so, read up on it in [wiki](https://github.com/bekkibau/deletecord/wiki) and use at your own risk the following features:
- non-mac m1
- non-chrome browser
- deleting messages from a channel
- NSFW
- Import
- after message id
- search message
- manually entering the `get` values

# contributing
I don't plan to maintain this regularly, but I can confirm it works as of this initial upload date. I might have to update it the next time I send a regrettable message to someone (hoping not for a while). If [victornpb/undiscord](https://github.com/victornpb/undiscord) becomes active again, I'll likely cherry-pick commits into this fork to have my own copy. 

I'll accept easy to review changes (eg. few lines of code & test screenshots) or steps on how to make it work for other browser / OS.

# references

this is a modification of [victornpb/undiscord](https://github.com/victornpb/undiscord) which hasn't been updated in over a year, so i forked it to fix small bugs. I've only fixed the bugs that made the script pause or quit prematurely - i didn't add any new features.

If this ever breaks, I recommend you first check out: 
- [victornpb userscript](https://greasyfork.org/en/scripts/406540-undiscord)
- [victornpb gist](https://gist.github.com/victornpb/135f5b346dea4decfc8f63ad7d9cc182)
- [victornpb discussions](https://github.com/victornpb/undiscord/discussions)

# Privacy Policy
Though I am a fork, I adhere to the original creator's [Privacy Policy](https://github.com/bekkibau/deletecord/wiki/Security-Policy)
