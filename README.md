# blog
experimental blog using github

Idea : use the github commit history to determine updates to a blog post. Work out some conventions and stick to them, build a simple site, or use the static site generator?

## January 2017

### speeding up backups on mac

#### 26.01.17

My backups started running very slowly, even when I was backing up to a local USB disk, and would sometimes look like they had 'hung' for hours. After changing 

1. use external usb, don't do over network. (obvious)
1. exclude your `java android sdk` folders, these contain gigabyte files. (You'll have some big files here if you do any android, xamarin, ios, ionic dev work.)
1. exclude any vmware, virtualbox files, etc.
1. temporarily disable sophos `live protection`. At the very least disable during the first big backup, backing up for the first time.
1. In some circumstances, test to see if helps, can temporarily give backup process higher priority `sudo sysctl debug.lowpri_throttle_enabled=0`. (I believe this might give ***all*** debug processes higher priority, so this needs further investigation)
1. when finished backing up, restart, reboot or reset debug priorities.  `sudo sysctl debug.lowpri_throttle_enabled=1` (not 100% certain if this is correct?)

