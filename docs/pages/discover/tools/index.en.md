# Tools
## Hosting
### [Sia Host Manager](https://siacentral.com/host-manager)
An improved interface for Sia network hosts. Get accurate and complete statistics and monitor the health of your host. Replaces or runs alongside Sia-UI.

Sia Host Manager combines information from your Sia node as well as information from the blockchain to display more accurate financial and health statistics.

* Monitors connection status
* Add, remove and resize storage folders
* Get detailed information about ongoing, completed, and failed storage obligations
* Change host configuration
* Pin configuration prices to fiat or cryptocurrencies
* Display financials in different fiat or cryptocurrencies

## Renting
### [Decentralizer](https://keops.cc/decentralizer)
A tool for Sia renters that allows:

* Micro-managing and data visualization about the formed contracts.
* Creating filters of hosts, according to geolocation, Sia version, SiaStats performance score, pricing and/or manual selection.
* Detection of hosting farms and unsafe hosts, allowing cancelling contracts with them and/or filter them out. “Farms” represent multiple hosts sharing geolocation, most pprobably being controlled by the same opeprator. Centralization of hosts is problematic, as it implicates that redundant copies of the files are being stored in the same location (what defeats the purpose of the redundancy). It also exposes the renter to malicious hosts performing a sybil attack by denying acccess to files after controling a large enough number of hosts.

> Ready-to-use binaries for Windows, MacOS and Linux can be downloaded here: https://github.com/hakkane84/Decentralizer-GUI/releases

> Users of headless servers or preferring command line interfaces can use Decentralizer-CLI instead, which brings the same features: https://github.com/hakkane84/Decentralizer-CLI

### [Siasync](https://github.com/tbenz9)
Siasync is a utility that will monitor a folder and synchronize its contents to the Sia network. As new files are created or removed it will keep Sia in sync with the local source folder. Siasync also supports more advanced features like only syncing certain file extensions, or excluding certain file extensions, or archive mode which won’t delete files from Sia even if they are deleted locally. Best of all, it works on Windows, MacOS, and Linux.

### [Repertory](https://bitbucket.org/blockstorage)
Repertory allows you to mount Sia blockchain storage solution via FUSE on FreeBSD/FreeNAS/Linux/MacOS or via WinFSP on Windows.

## In Development
### [Papyrus](https://gitlab.com/lukehmcc/papyrus)
A simplified and modern UI to the Sia network build with `us` framework.
