# OpenWRT Zorp feed

## Description

This is the OpenWrt Zorp feed containing Zorp development team maintained packages.

## Usage

Add this line to your feeds.conf file:

src-git zorp https://github.com/balasys/zorp-openwrt-feed.git;6.0

To install all its package definitions:

Run: ./scripts/feeds update  zorp
Run: ./scripts/feeds install -a -p zorp

## License

See [LICENSE](LICENSE) file.

## Package Guidelines

See [CONTRIBUTING.md](CONTRIBUTING.md) file.
