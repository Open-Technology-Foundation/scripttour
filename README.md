# ScriptTour

A Bash 'script player' that executes and displays commands with typewriter-like effects, perfect for demos, tutorials, and presentations.

## Features

- Typewriter-style command and comment display
- Configurable typing speeds for commands and comments
- Custom username and hostname display
- Screen clearing capabilities
- Color-coded output (commands in yellow, comments in green)
- Error code tracking
- Support for silent commands and pauses

## Requirements

- Ubuntu Linux (or compatible distribution)
- Bash 5.0+
- Standard GNU utilities (grep, find, rsync, ssh, scp, sed, ls)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Open-Technology-Foundation/scripttour.git
cd scripttour
```

2. Make the script executable and symlink into /usr/local/bin:
```bash
chmod +x scripttour
ln -s "$PWD"/scripttour /usr/local/bin/scripttour
```

## Usage

Basic usage:
```bash
scripttour [OPTIONS] file.script
```

### Options

- `-c, --clear` - Clear screen and wait 5 seconds
- `-o, --comment-speed SPEED` - Set comment typewriter speed
- `-m, --cmd-speed SPEED` - Set command typewriter speed
- `-U, --username USER` - Set custom username
- `-H, --hostname HOSTNAME` - Set custom hostname
- `-v, --verbose` - Increase output verbosity
- `-q, --quiet` - Suppress non-error messages
- `-V, --version` - Print version and exit
- `-h, --help` - Display help

SPEED: xxxfast xxfast xfast vfast fast normal slow vslow xslow xxslow xxxslow

### Example Usage

Simple playback:
```bash
scripttour motivation.se.script
```

Advanced configuration:
```bash
./scripttour -c -o xfast -m fast -U sysadmin -H yatti.id motivation.se.script
```

## Script File Format

The script file (.script) supports several special syntax features:

- `##` - Silent comment (ignored)
- `#` - Displayed comment (typed out)
- `!` - Silent command execution
- Empty lines - 1-second pause
- Numbers alone - Sleep for specified seconds
- Regular commands - Executed and displayed

Example script file:

```bash
## This is a silent comment
# This comment will be typed out using typewriter
ls -la
!echo "This command runs silently"
5
pwd

```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the GPL3 License - see the LICENSE file for details.

## Version

Current version: 1.0.2

## Author

Gary Dean

## Acknowledgments

- Thanks to all contributors and testers
- Inspired by various demo tools and presentation utilities

