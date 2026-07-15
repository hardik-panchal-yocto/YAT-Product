# YAT Sample Outputs

This document provides representative command output examples for **YAT (Yocto Automation Tool) Community Edition**.

The examples below are intended for demonstrations, product evaluations, and documentation purposes.

All paths, timestamps, and values shown are illustrative and do not represent actual customer or project data.

---

## Example: yat info

```bash
$ python3 yat.py info

==========================================
            YAT - Yocto Automation Tool
==========================================

Version     : v0.2-alpha
Author      : Hardik Panchal
Purpose     : Yocto workflow automation
Language    : Python 3
Platform    : Linux

Current Features
----------------
- Environment Diagnostics
- Build Management
- Build Cleanup
- Log Analysis
- Reporting
- Build History
- Build Statistics
- Export Functionality

==========================================
```

---

## Example: yat status

```bash
$ python3 yat.py status

=========== YAT System Status ===========

OS              : Linux 6.8
Machine         : x86_64
CPU Threads     : 16

Root Disk Total : 500 GB
Root Disk Free  : 320 GB

Yocto Path      : FOUND (/home/user/poky)

=========================================
```

---

## Example: yat config --show

```bash
$ python3 yat.py config --show

=========== YAT Configuration ===========

Yocto Path      : /home/user/poky
Build Directory : /home/user/poky/build

Status          : VALID

=========================================
```

---

## Example: yat doctor

```bash
$ python3 yat.py doctor

==========================================
           YAT Doctor Check
==========================================

[PASS] Yocto path exists
[PASS] Yocto build directory exists
[PASS] Free disk space
[PASS] UTF-8 locale configured
[PASS] CPU thread detection
[PASS] Network connectivity

Checking required tools:

  [OK] git
  [OK] gcc
  [OK] make
  [OK] python3
  [OK] tar
  [OK] wget
  [OK] diffstat
  [OK] unzip
  [OK] xz
  [OK] lz4
  [OK] zstd

==========================================
Environment Status : HEALTHY
==========================================
```

---

## Example: yat build --dry-run core-image-minimal

```bash
$ python3 yat.py build --dry-run core-image-minimal

==========================================
      YAT Build Dry Run Started
==========================================

Image       : core-image-minimal
Yocto Path  : /home/user/poky
Build Dir   : /home/user/poky/build

Mode        : Dry Run

==========================================
      Build Dry Run Summary
==========================================

Image        : core-image-minimal
Duration     : 2 seconds
Result       : SUCCESS

Next Suggested Command

python3 yat.py build core-image-minimal

==========================================
```

---

## Example: yat logs --latest

```bash
$ python3 yat.py logs --latest

==========================================
          Latest Build Log
==========================================

File:

build/tmp/log/cooker/qemux86-64/build.log

Last Modified:

2026-07-11 10:45:03

Status:

AVAILABLE

==========================================
```

---

## Example: yat analyze

```bash
$ python3 yat.py analyze

==========================================
         YAT Build Log Analysis
==========================================

Log File:

build/tmp/work/qemux86-64/core-image-minimal/temp/log.do_compile

Build Status:

FAILED

Failed Task:

do_compile

------------------------------------------
Summary
------------------------------------------

ERROR Count   : 2
WARNING Count : 1

------------------------------------------
Recent Errors
------------------------------------------

ERROR: Task (core-image-minimal.bb:do_compile) failed

ERROR: No space left on device

------------------------------------------
Recent Warnings
------------------------------------------

WARNING: Build directory is using a large amount of disk space

------------------------------------------
Detected Issues
------------------------------------------

Issue #1

Category      : Disk Space Issue

Pattern       : No space left on device

Recommendation: Free disk space, Clean Yocto tmp directory, Remove old build artifacts or Consider moving the build directory to a larger partition

Severity      : HIGH

------------------------------------------

Analysis Result

Status        : ACTION REQUIRED

==========================================
```

---

## Example: yat report

```bash
$ python3 yat.py report

=========== YAT Project Report ===========

Yocto Path      : /home/user/poky
Path Status     : FOUND

Build Directory : /home/user/poky/build
Build Status    : READY

MACHINE         : qemux86-64

Disk Total      : 500 GB
Disk Used       : 180 GB
Disk Free       : 320 GB

Deploy Directory:

build/tmp/deploy/images/qemux86-64

Recent Artifacts:

- core-image-minimal-qemux86-64.wic
- core-image-minimal-qemux86-64.tar.bz2

==========================================
```

---

## Example: yat history

```bash
$ python3 yat.py history

=============== Build History ===============

Image       : core-image-minimal
Status      : SUCCESS
Duration    : 25 minutes

---------------------------------------------

Image       : core-image-minimal
Status      : FAILED
Duration    : 10 minutes

---------------------------------------------

Total Entries: 2

=============================================
```

---

## Example: yat history --success

```bash
$ python3 yat.py history --success

=============== Successful Builds ===============

core-image-minimal
core-image-full-cmdline

Total Successful Builds: 2

=================================================
```

---

## Example: yat stats

```bash
$ python3 yat.py stats

============= Build Statistics =============

Total Builds         : 12
Successful Builds    : 10
Failed Builds        : 2

Success Rate         : 83.3%

Average Build Time   : 22 minutes
Fastest Build        : 11 minutes
Slowest Build        : 37 minutes

Last Build
-------------------------------------
Image                   : core-image-minimal
Status                  : SUCCESS
Start Time              : 2026-07-08 18:05:51.311701
duration                : 17 minutes
=============================================
```

---

## Example: yat export report

```bash
$ python3 yat.py export report

Export Successful

File:

/home/user/yat/exports/project_report_2026-07-11_10-15-30.txt
```

---

## Example: yat export history

```bash
$ python3 yat.py export history

Export Successful

File:

/home/user/yat/exports/build_history_2026-07-11_10-15-30.txt
```

---

# Summary

These examples demonstrate how YAT helps Yocto developers:

- Validate development environments
- Execute and monitor builds
- Analyze build failures
- Generate project reports
- Track build history
- Review build statistics
- Export project information

YAT Community Edition focuses on improving developer productivity and reducing manual effort in day-to-day Yocto development workflows.

