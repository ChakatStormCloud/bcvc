# Bandcamp Volume Control

## Source Repo

[bandcamp-volume-control @ GitLab](https://gitlab.com/markoooo/bandcamp-volume-control) | [bandcamp-volume-control @ GitHub](https://github.com/butterknight/bandcamp-volume-control)

## Foreword

I didn't write this, but the original version is no longer updated. I forked and made this so I can add non-bandcamp domains and provide further utility to this extension/addon.

## Download

Available for download on the [Firefox AMO](https://addons.mozilla.org/en-US/firefox/addon/bandcamp-volume-control/) or [Chrome Web Store](https://chrome.google.com/webstore/detail/bandcamp-volume-control/pbbndlbppenfhgnkkcmkcmeodbfkgimf).

## How this thing works

The extension works by searching for HTML5 audio players on any Bandcamp page (including the embedded players on other websites), hooking into their HTML markup where the buttons (well, Play/Pause button) and progress slider are and adding in a volume slider that can control said player's volume. 

The slider takes some of the styles from Bandcamp's own player to fit the visual style so it should look fairly consistent. It's nothing too fancy, but it gets the job done. The volume slider handle is a bit more rounded to make it easier to discern it from the regular song progress bar.

The volume is saved every time it's changed and the value should persist across multiple players. So if you save a volume at 42% on one page and open up another one (it doesn't matter if it's embedded or not), the volume should default to 42% in that one, too. This eliminates the need to constantly reset it if you're browsing multiple pages quickly. Note that if there are multiple embedded players in the same page, changing volume of one will **not** instantly affect any other. Also, only the last value changed (regardless of the player) will be saved.

## Important notices

Note: This section may be out of date and require updating.

* Currently on Bandcamp's Discover page one slider controls **all** found audio player page elements until I figure out which is which. I don't use that page enough to actually know the consequences of that yet
* There is an issue with artwork-only player where the volume slider interferes with the playlist that shows up on hover; I'll see about getting that fixed as soon as I can
* Those very tiny players aren't currently supported at all

## Permissions

The extension requires:

* The `storage` permissions so it can save the volume level.
* Access to the content of any Bandcamp (`https://*.bandcamp.com/`) page (so it can find the player, markup, etc.).
* Access to certain `bandcamp.com` sites with custom domains (such as `music.monstercat.com`).

## How To Build This

Building this is kinda of a pain since you have to use an old version of nodejs...

* Install [node v10.22.1](https://nodejs.org/en/blog/release/v10.22.1/) (any v10.x *should* probably work)
* Clone this repo
* From the repo directory, run `npm run build-prod`
* Output is in `./build`
