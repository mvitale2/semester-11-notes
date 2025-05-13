## Necessary Features
* **real-time DM text messaging**
* **real-time group discord-server-esque messaging**
	* **ability to add and remove text/voice channels in said servers**
* real-time 1-on-1 voice communication
* **the ability to create servers**
	* **ability to create multiple channels in servers**
* file uploading
	* images
* SIZE LIMIT FOR UPLOADING
* image previews (embedding images)
* **the ability to make accounts/profiles**
	* **username**
	* pfp
	* **password**
* **customization of group "servers"**
	* **title**
	* **icon/banner**
	* **channel names**
* adding/removing users from groups
* **adding/removing users from friends**
* **users being able to remove themselves from** groups/**DMs**
* deleting a DM/server (only if owner)
## Nice Features
* dark/light mode (EWWWWWWWWWWWWWWWW)
* voice channels
* voice communication IN voice channels
* from an admin view only, be able to restrict users from accessing certain text/voice channels
	* tag system where everyone joins as a default tag that can be edited to restrict access to certain channels, owner can manually add/change tags to allow different users different tiers of access
	* NOTE: no additional admin roles can be assigned (this app is meant to be for smaller groups that should only REQUIRE one admin (the owner))
* transfer ownership of server/DM
* markdown integration
* deletion of individual channels in a server
* deletion of individual messages
* editing messages (only your own)
## Optional Features
* file uploading
	* audio
	* videos
	* docs
* real-time text appearance
* change color of username

## Features to be Evaluated


## Tag System Example
public forum
private employee chat

User1 - employee (all access)
User2 - forum-only
User3 - forum-only
ADMIN ACTION
User3 - employee (all access)


## Schedule Breakdown
* Prototype Interface (don't spend too much time on this)
	* little bit of css as well
* Setup account system in supabase
	* ONLY DO 2 FIELDS FOR NOW - username/password
* Real time DM messaging (with supabase)
* Implement friends system where users can friend each other
* Implement user management functions
	* Adding/removing users from friends
	* Users removing themselves from DMs
* Server/server creation features
	* Channel creation/deletion features
	* Customization - title, icon, banner, channel names
* Image functionality
	* 