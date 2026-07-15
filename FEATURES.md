# YAT Features

This document describes the core capabilities of YAT, the Yocto Automation Tool for the YAT Community Edition. It is intended for developers, maintainers, and embedded Linux teams who want a structured and efficient way to work with Yocto-based projects.

## Current Edition

- Edition: Community Edition
- Version: v0.2-alpha
- Status: Active Development

## Environment Management

### Configure Yocto Workspace
Configure the Yocto project path used by YAT.

Example:
```bash
python3 yat.py config --path /path/to/poky
```

### Show Current Configuration
Display the currently configured Yocto workspace.

Example:
```bash
python3 yat.py config --show
```

## Build Management

### Build an Image
Start a Yocto build for a specified target image.

Example:
```bash
python3 yat.py build core-image-minimal
```

### Dry Run Build
Preview build execution without running the full build.

Example:
```bash
python3 yat.py build --dry-run core-image-minimal
```

## Cleaning Management

### Clean Recipe Output
Remove recipe build artifacts for a selected recipe.

Example:
```bash
python3 yat.py clean image busybox
```

### Clean Shared State (sstate)
Remove sstate artifacts for a recipe.

Example:
```bash
python3 yat.py clean sstate busybox
```

### Clean All Recipe Outputs
Remove all related build outputs for a recipe.

Example:
```bash
python3 yat.py clean all busybox
```

### Clean Build Temporary Files
Remove temporary build directories and files.

Example:
```bash
python3 yat.py clean tmp
```

## Log Management

### View Recent Logs
Display recent Yocto logs.

Example:
```bash
python3 yat.py logs
```

### View Latest Log
Open the most recent relevant log entry for immediate troubleshooting.

Example:
```bash
python3 yat.py logs --latest
```

## Analysis and Diagnostics

### Environment Diagnostics
Validate the Yocto environment and identify common issues.

Example:
```bash
python3 yat.py doctor
```

### Analyze Latest Log
Analyze the most recent log file.

Example:
```bash
python3 yat.py analyze --latest
```

### Analyze a Specific Log File
Perform targeted analysis on a chosen log file for deeper troubleshooting.

Example:
```bash
python3 yat.py analyze --file /path/to/logfile
```

## Reporting

### Generate Project Report
Produce a summary report of the current Yocto project state, environment, and key build-related information.

Example:
```bash
python3 yat.py report
```

## Build History

### Review Build History
Display recent build history.

Example:
```bash
python3 yat.py history
```

### Show Recent Build History
Display a limited number of recent build entries for quick review.

Example:
```bash
python3 yat.py history --last 5
```

### Filter Successful Builds
Display only successful builds.

Example:
```bash
python3 yat.py history --success
```

### Filter Failed Builds
Display only failed builds.

Example:
```bash
python3 yat.py history --failed
```

### Review Builds by Image
Focus history on a specific image name to analyze build trends.

Example:
```bash
python3 yat.py history --image core-image-minimal
```

## Build Statistics

### Show Build Statistics
Present summarized metrics about build success, failure, and historical build activity.

Example:
```bash
python3 yat.py stats
```

### Show Statistics for a Specific Image
Review build statistics for a selected image target.

Example:
```bash
python3 yat.py stats --image core-image-minimal
```

## Exporting

### Export Build History
Export build history for offline review.

Example:
```bash
python3 yat.py export history
```

### Export Project Report
Export a generated project report for documentation, support, or reporting purposes.

Example:
```bash
python3 yat.py export report
```

## Community Edition Scope

Current Community Edition capabilities include:

- Environment Diagnostics
- Build Execution and Dry-run support
- Log Analysis and Troubleshooting
- Project Reporting
- Build History Tracking
- Build Statistics and Analytics
- Exportable Reports
- Configuration Management

## Summary

YAT Community Edition helps Yocto developers improve productivity through:

- Structured workflow automation
- Faster log analysis and troubleshooting
- Better project visibility
- Consistent build diagnostics
- Historical tracking and reporting
- Improved operational efficiency

Additional capabilities are planned for future releases and are documented in [ROADMAP.md](ROADMAP.md).
