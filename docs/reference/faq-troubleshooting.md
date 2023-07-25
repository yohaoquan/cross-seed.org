# FAQ & Troubleshooting

## What can I do about `error parsing torrent at http://…`?

This means that the jacket download link didn't resolve to a torrent file. It's
possible you got rate-limited so you might want to try again in a day or more.
Otherwise, just ignore it. There's nothing cross-seed will be able to do to fix
it.

## rtorrent injected torrents don't check (or start at all) until force rechecked
Remove any `stop_untied=` schedules from your .rtorrent.rc.

Commonly: `schedule2 = untied_directory, 5, 5, (cat,"stop_untied=",(cfg.watch),"*.torrent")`

## Failed to inject, saving instead.
This could be caused by a number of reasons. Check the verbose log:

### 1. `injection failed: Failed to retrieve data dir; torrent not found in client`
This is caused by not having your download client set up to grab torrents from the cross-seed's output folder automatically.

#### qBittorrent
1. Make sure the `outputDir` folder in config.js is visible to your target qBittorrent instance at `qbittorrentUrl` in `config.js`.
2. go to qBittorrent's `Options` -> `Downloads` -> `Automatically add torrents from:` and add the folder you specified as `outputDir` in cross-seed, and the save location as default.
3. Save

#### Transmission
TODO

#### rTorrent 
TODO


