## Worktips Lite (GUI Wallet)

This is the reference code for [Worktips](https://worktips.info) cryptocurrency.

* Official homepage: [Worktips](http://worktips.info)
* Official repository: [Worktips GitHub](https://github.com/Vordas/worktips)
* Official Announcement thread: [Worktips BitcoinTalk](https://bitcointalk.org/index.php?topic=3086019.0)
* Official Discord: [Worktips Discord](https://discord.gg/UmZExyz)
* Official Facebook: [Worktips Facebook](https://www.facebook.com/worktipscoin)
* Official Twitter: [Worktips Twitter](https://twitter.com/wtipscoin)
* Official Telegram: [Worktips Telegram](https://t.me/joinchat/HOvygRE-6UnWOzoh72NVMA)
* Official Whitepaper: [Worktips Whitepaper](http://worktips.info/whitepaper_worktips.zip)
* Official Block explorer: [Worktips Block explorer](http://blockexplorer.worktips.info)

## Features

- CPU miner support (set core number)
- Remote node syncing
- No local blockchain files
- Transfer WTIP
- Address book
- CSV export
- Full transactions history
- Open/backup wallets
- Import/export wallet keys
- Create wallet
- Encrypt wallet


## How to compile

### Compile on Linux Ubuntu 16.04

**1. Install dependencies**

```
sudo apt-get update
sudo apt-get install -y build-essential python-dev gcc-4.9 g++-4.9 git cmake libboost-all-dev librocksdb-dev tmux qt5-default qttools5-dev-tools software-properties-common tk8.5 tcl8.5 zip unzip
```

**2. Clone the repository**

```
git clone https://github.com/Vordas/worktips-lite.git worktipslite
```

**3. Get the coin source**

```
cd worktipslite
git clone https://github.com/Vordas/worktips.git cryptonote
```

**4. Fetch the rocksdb lib**

```
cd
cd worktipslite/lib
wget http://worktips.info/libs/linux/rocksdblib.lib
chmod +x rocksdblib.lib
```

**5. CHMOD**

```
cd
cd worktipslite/cryptonote/external/rocksdb/build_tools
chmod +x build_detect_platform
chmod +x version.sh
```

**6. Build**

```
cd
cd worktipslite
mkdir build
cd build
cmake -DSTATIC=ON -DCMAKE_BUILD_TYPE=RELEASE ..
export CXXFLAGS="-std=gnu++11"
make
```

_Your executables will be located in `build/release` folder._