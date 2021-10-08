---
title: "Random internal things"
layout: single
---

* Common [.bash_profile](bash_profile.txt)
* For Linux group members (e.g., those members of BIDS-HPC) to create files that are accessible by other group members, add `umask 002` to their `.bashrc`
* Commands for ensuring permissions are set on files/directories in relevant folders:

```bash
chmod -R g=u,o=u-w public # where public is a public directory
chmod -R g=u,o-rwx private # where private is a group-only directory
```
