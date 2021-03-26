# Systemctl timers

## Show all timers 

```
# alle Timer anzeigen 
systemctl list-timers 
```

## How ? 

 * .timer and .service file next to each other 

## Example ? 

```
# timer - file 
root@ubuntu2004-104:/etc# systemctl cat systemd-tmpfiles-clean.timer
# /lib/systemd/system/systemd-tmpfiles-clean.timer
#  SPDX-License-Identifier: LGPL-2.1+
#
#  This file is part of systemd.
#
#  systemd is free software; you can redistribute it and/or modify it
#  under the terms of the GNU Lesser General Public License as published by
#  the Free Software Foundation; either version 2.1 of the License, or
#  (at your option) any later version.

[Unit]
Description=Daily Cleanup of Temporary Directories
Documentation=man:tmpfiles.d(5) man:systemd-tmpfiles(8)

[Timer]
OnBootSec=15min
OnUnitActiveSec=1d


## Service - file 
root@ubuntu2004-104:/etc# systemctl cat systemd-tmpfiles-clean.service
# /lib/systemd/system/systemd-tmpfiles-clean.service
#  SPDX-License-Identifier: LGPL-2.1+
#
#  This file is part of systemd.
#
#  systemd is free software; you can redistribute it and/or modify it
#  under the terms of the GNU Lesser General Public License as published by
#  the Free Software Foundation; either version 2.1 of the License, or
#  (at your option) any later version.

[Unit]
Description=Cleanup of Temporary Directories
Documentation=man:tmpfiles.d(5) man:systemd-tmpfiles(8)
DefaultDependencies=no
Conflicts=shutdown.target
After=local-fs.target time-set.target
Before=shutdown.target

[Service]
Type=oneshot
ExecStart=systemd-tmpfiles --clean
SuccessExitStatus=DATAERR
IOSchedulingClass=idle

```

## Example Reference 


  * https://www.tutorialdocs.com/article/systemd-timer-tutorial.html


## Personal Timer (timer for user) 

  * https://nielsk.micro.blog/2015/11/11/creating-systemd-timers.html
