# blog
experimental blog using github

Idea : use the github commit history to determine updates to a blog post. Work out some conventions and stick to them, build a simple site, or use the static site generator?

## January 2017

### speeding up backups on mac

#### 26.01.17

My backups started running very slowly, even when I was backing up to a local USB disk, and would sometimes look like they had 'hung' for hours. The following fixed it for me.

**It's such a Pity Moore's Law never applied to backups!**

- use external usb 3 on a thunderbolt connection, don't do over network. (obvious)
- exclude your `java android sdk` folders, these contain gigabyte files. (You'll have some big files here if you do any android, xamarin, ios, ionic dev work.)
- exclude any vmware, virtualbox files, etc.
- temporarily disable sophos `live protection`. At the very least disable during the first big backup, backing up for the first time.
- In some circumstances, test to see if helps, can temporarily give backup process higher priority `sudo sysctl debug.lowpri_throttle_enabled=0`. (I believe this might give ***all*** debug processes higher priority, so this needs further investigation)
- when finished backing up, restart, reboot or reset debug priorities.  `sudo sysctl debug.lowpri_throttle_enabled=1` (not 100% certain if this is correct?)
- Result? I've gone from a backup not being able to calculate the time remaining to, 8 hours left, finally to around 4 hours to backup around 400gb, which is about right.

![Time machine finally backing up at a somewhat decent speed](img/2017-01-time-machine-finally-backing-up-faster.png)


