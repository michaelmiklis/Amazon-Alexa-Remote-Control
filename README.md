# Amazon-Alexa-Remote-Control
Shell script for Amazon Alexa Remote Control. The script was developed by Alexander Noak:
[http://blog.loetzimmer.de/2017/10/amazon-alexa-hort-auf-die-shell-echo.html](http://blog.loetzimmer.de/2017/10/amazon-alexa-hort-auf-die-shell-echo.html)

I extended the script for reading Alexa Alarms by using the "-n" parameter

	G090LV03XX6709XX 20:20:00.000 ON
	G090LV03XX6709XX 07:30:00.000 OFF

It will return all set up alarms, the device serial number and the alarm state (on | off).

## Usage
	./alexa_remote_control.sh [-d <device>|ALL] -e <pause|play|next|prev|fwd|rwd|shuffle|vol:<0-100>> | -b [list|<"AA:BB:CC:DD:EE:FF">] | -q | -r <"station name"|stationid> | -s <trackID> | -t <ASIN> |
			 -u <seedID> | -v <queueID> | -w <playlistId> | -i | -p | -P | -S | -a | -m <multiroom_device> [device_1 .. device_X] | -lastalexa | -l | -h
	   -e : run command
	   -b : connect/disconnect/list bluetooth device
	   -q : query queue
	   -r : play tunein radio
	   -s : play library track
	   -t : play Prime playlist
	   -u : play Prime station
	   -v : play Prime historical queue
	   -w : play library playlist
	   -i : list imported library tracks
	   -p : list purchased library tracks
	   -P : list Prime playlists
	   -S : list Prime stations
	   -a : list available devices
	   -m : delete multiroom and/or create new multiroom containing devices
	   -lastalexa : print device that received the last voice command
	   -l : logoff
	   -h : help


## Change-Log:
	 2017-10-10: v0.1 initial release
	 2017-10-11: v0.2 TuneIn Station Search
	 2017-10-11: v0.2a commands on special device "ALL" are executed on all ECHO+WHA
	 2017-10-16: v0.3 added playback of library tracks
	 2017-10-24: v0.4 added playback information
	 2017-11-21: v0.5 added Prime station and playlist
	 2017-11-22: v0.6 added Prime historical queue and replaced getopts
	 2017-11-25: v0.6a cURL is now configurable
	 2017-11-25: v0.7 added multiroom create/delete, playback of library playlist
	 2017-11-30: v0.7a added US config, fixed device names containing spaces
	 2017-12-07: v0.7b added Bluetooth connect/disconnect
	 2017-12-18: v0.7c fixed US version
	 2017-12-19: v0.7d fixed AWK csrf extraction on some systems
	 2017-12-20: v0.7e moved get_devlist after check_status
	 2018-01-08: v0.7f added echo-show to ALL group, TuneIn station can now be up to 6 digits
	 2018-01-08: v0.8 added bluetooth list function
	 2018-01-10: v0.8a abort when login was unsuccessful
	 2018-01-25: v0.8b added echo-spot to ALL group
	 2018-01-28: v0.8c added configurable browser string
	 2018-02-17: v0.8d no need to write the cookie file on every "check_status"
	 2018-02-27: v0.8e added "lastalexa" option for HA-Bridge to send its command to a specific device
	  (Markus Wennesheimer: https://wennez.wordpress.com/light-on-with-alexa-for-each-room/)
	 2018-02-27: v0.9 unsuccessful logins will now give a short info how to debug the login
	 2018-03-09: v0.9a workaround for login problem, force curl to use http1.1

