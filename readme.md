# rove-scan
`rove-scan` is a simple dashboard for rove to display the connection status for rove during ELROB 2026.

## Setup
Install dependencies
```bash
pip install -r requirements.txt
```

Add `.local/bin` to path (if you want to use it from anywhere). Add this to your `.bashrc`/`.zshrc`
```bash
export PATH=$PATH:~/.local/bin
```

Make sure `.local/bin` exists and link the file there
```bash
mkdir -p ~/.local/bin
ln -s /path/to/rove-scan ~/.local/bin/rove-scan
```

## Usage

```bash
usage: rove-scan [-h] [-i INTERVAL] [-t TIMEOUT] [-l LOG] [--discover-url DISCOVER_URL]
                 [--no-discover] [--once] [-c] [--show-self]

Live network status dashboard.

options:
  -h, --help            show this help message and exit
  -i, --interval INTERVAL
                        seconds between refreshes (default: 2)
  -t, --timeout TIMEOUT
                        ping timeout in seconds (default: 1)
  -l, --log LOG         log file path (default: netmon.log)
  --discover-url DISCOVER_URL
                        sensor discovery endpoint (default: http://192.168.2.2:8080/discover)
  --no-discover         disable the /discover sensor monitor
  --once                print a single snapshot and exit
  -c, --compressed      flat view: no categories, no spacing
  --show-self           don't hide this machine's own IP
```

## Following the log
In case you want to see the log in realtime, you can run this:
```bash
tail -f ./netmon.log
```

