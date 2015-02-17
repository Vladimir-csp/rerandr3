# rerandr3
Bash multimonitor handler daemon next gen

syntax:

	rerandr3 command

where *command* is one of:

*save* - save current uniqe monitor setup based on output names,
monitor models and serial numbers from EDID data.

*restore* - if current monitor setup is known, apply stored config.
If setup is unknown, try to disable everything disconnected and
enable and stack everything connected.

*show* - dump setup ID and xrandr arguments of current state

*daemon* - launch user session daemon for automatic triggering.

*trigger-save* - tell daemon to do save.

*trigger-restore* - tell daemon to restore configuration.


to use rerandr3 in 'full auto', create udev rule:

	KERNEL=="card0", SUBSYSTEM=="drm", RUN+="/usr/local/bin/rerandr3 trigger-restore"

where "/usr/local/bin/rerandr3" is the full path to this script
