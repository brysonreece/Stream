Stream
===========
A fork of ['XBMCtorrent'](https://www.github.com/steeve/XBMCtorrent) by steeve

What is it?
----------
Stream allows you to stream magnet links from within XBMC, without having to wait for the whole file to download, thanks to sequential downloading (see FAQ).



Screenshots
------------
![Choose from different types of media!](http://i.imgur.com/2tKqKjg.png "Choose from different types of media!")
![Enjoy your favorite TV shows...](http://i.imgur.com/LeHstnd.png "[Enjoy your favorite TV shows...")
![...and even your favorite movies!](http://i.imgur.com/fIPnUie.jpg?1 "...and even your favorite movies!")


How It's Different
-------------------
One of the noticeable differences between Stream and XBMCtorrent is the user interface. XBMCtorrent provides a basis for accessing media while Stream helps offer better categorical organization, media headings, and plenty of backend upgrades. Want to give it a shot? [Download today!](http://stream.brysonreece.com/)



Download
--------
Check out the [Stream website](http://stream.brysonreece.com/) to download the ZIP file.



Supported Platforms
-------------------
* Windows x32 and x64
* OS X x32 and x64
* Linux x32 and x64
* Raspberry Pi
* Android 4.0+

How it works
------------
Stream is actually two parts:
* 'Stream': the modified XBMCtorrent addon written in Python.
* `torrent2http`: a custom bittorrent client written in Go and leveraging libtorrent-rasterbar, that turns magnet links into HTTP endpoints, using sequential downloading.

If you feel adventurous, you can find the `torrent2http` and `libtorrent-go` sources by steeve at:
* https://github.com/steeve/libtorrent-go
* https://github.com/steeve/torrent2http



FAQ
---
#### How do I install Stream?
Simply download the latest version [here,](http://stream.brysonreece.com/) navigate to your XBMC settings/Addons, choose 'Install from zip', navigate to where you downloaded Stream, select it, and enjoy!

#### Does it work with all torrents?
It works with most. Occasionally, some torrents are known not to work.

#### The plugin doesn't work at all, what can I do?
First of all, we need to make sure it's not the torrent's fault. Test this by initiating another download. If it doesn't work, post an issue along with your xbmc.log.

#### Can I seek in a video?
Yes, although now if you try to seek to a part you haven't downloaded yet, XBMC will wait for that part to be available.

#### Can it stream HD?
Of course! 720p and 1080p work fine, provided you have enough bandwidth, and there are enough people seeding the torrent.

#### Isn't sequential download on bittorrent is bad?
Generally, yes. However, Stream respects the same [requirements "defined" by uTorrent 3](http://www.utorrent.com/help/faq/ut3#faq2[/url]). Also, Stream tries to make it up by seeding while you watch the movie.

#### Does it download the whole file? Do I need the space? Is it ever deleted?
Yes, yes, and yes. Stream will pre-allocate the whole file before download. So if you want to watch a 4GB video, you'll need the 4GB available on your storage medium. The file is deleted once you stop watching it, unless you choose to keep files from within the addon settings.

#### Where is the file located? Can I change it?
Currently the file is downloaded in the same directory as the torrent2http executable by default (in resources/bin/<OS>/ in the addon directory). You can change this location from within Stream's settings.

#### Can I keep the file after playback?
Yes, just enable this option in the addon settings.

#### Can I set it to download directly to my NAS and keep it after playback?
Just set the download directly to your NAS location, and make sure you have enabled "Keep files after playback" option.

#### Why are you using Google Analytics? Can I disable it?
Short answer: In order to gain analytics about how many people use Stream.

Long answer: First of all, your whole IP isn't tracked. Only the first 3 parts of it, thanks to Analytics [Anonymous Mode](https://developers.google.com/analytics/devguides/collection/gajs/methods/gaJSApi_gat?csw=1#_gat._anonymizeIp). So for instance, if your IP is A.B.C.D, only A.B.C.0 will be logged.
Second, this is my only tool to track audience interest, this is great information, and it really helps.
Finally if you really want to, you can disable it in the addon settings (except for 1 GA event when you go in the addon).
If you are blocking GA on your computer altogether, you'll still be able to use the addon.

#### How can I report a bug?
Please, file an issue.

<!-- #### How can I use the Play-to-XBMC feature?
First, install [Play-to-XBMC](https://chrome.google.com/webstore/detail/play-to-xbmc/fncjhcjfnnooidlkijollckpakkebden) from khloke.
Then, follow the Play-to-XBMC install instructions:

> Setup:
>
> * On XBMC, go under System > Settings > Services > Webserver
> * Enable "Allow control of XBMC via HTTP, leave the port as default or set it to something else (if you know what you're doing). Write down the port number.
> * Username and password are optional
> * Right click on the 'Play to XBMC' icon and select 'Options'
> * Put in the IP address or hostname of your XBMC box and fill in the port number with the port number you wrote down earlier. Fill in the username and password if you entered one into XBMC.

Once you've done all that, simply right click on any magnet link, and select Play-to-XBMC > Play. Boom.
-->
#### Provider X is blocked in my country/ISP, how can I set another domain?
Enable Auto-Unblock in the settings.
If it still doesn't work, you can go in Advanced > Custom Domains. Here to you can set each provider with whatever proxy you choose.

Changelog
---------
Check out the [Releases](https://github.com/brysonreece/stream/releases) tab.



_Shoutout to [nessus](http://forum.xbmc.org/member.php?action=profile&uid=47428) for the amazingly-awesome [Bello](http://forum.xbmc.org/showthread.php?tid=158577) skin_
