# node-crawler
Reads the `peers.dat` file and attempts to connect the locally running node to the nodes seen the past 24 hours on the network.

## Dependencies
- Compiled `bitpeers` binary
- `jq` installed
- running, most recently released and synchronized `verusd` coin daemon.

## Installation
1. Compile `bitpeers` from https://github.com/RaghavSood/bitpeers using `Go`. Easy instructions can be found
  here https://raghavsood.com/blog/2018/05/20/demystifying-peers-dat in the final paragraph. Alternatively use
  the supplied binary, included in the release.
2. Edit lines 5-8 of the `crawl` script, to suit your situation

## Usage
You can either start the script manually or schedule it. The script will use `bitpeers` to read the currently present nodes
in your `peers.dat` and will select the IPs that have been reported active on the network to try connecting to.
When finished, it will create 2 files in binaries folder: one with the amount of connectable nodes and one with reported
active, yet unconnectable nodes for the past 24 hours. (Unconnectable nodes probably do not have public ports open or have switched off)


Special thanks to **Raghav Sood** for his `bitpeers` programming.
© Oink 2021
