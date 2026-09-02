# macports-upkeep

A self-hosted [MacPorts](https://www.macports.org) port repository for [upkeep](https://github.com/teknikqa/upkeep). MacPorts has no "tap" concept like Homebrew, so this is a plain Portfile repo that you add as a local source.

## Install

1. Clone this repo somewhere permanent:

   ```bash
   git clone https://github.com/teknikqa/macports-upkeep.git ~/.macports-upkeep
   ```

2. Add it to `/opt/local/etc/macports/sources.conf`, **above** the `[default]` line:

   ```
   file:///Users/<you>/.macports-upkeep
   rsync://rsync.macports.org/macports/release/tarballs/ports.tar [default]
   ```

3. Install:

   ```bash
   sudo port install upkeep
   ```

## Updating

```bash
cd ~/.macports-upkeep && git pull
sudo port selfupdate
sudo port upgrade upkeep
```

The `PortIndex` in this repo is regenerated automatically by CI whenever the `Portfile` changes, so a `git pull` is all you need locally — no manual `portindex` step.

## Maintenance

The `Portfile`'s `version` and `checksums` are updated automatically by `upkeep`'s release workflow whenever a new tag is pushed.
