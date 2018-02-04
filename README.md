# Nipper (desktop/mobile app)
See [thcolin/nipper](https://github.com/thcolin/nipper)

## Thoughts
* `WebView` or `Native` ?
  * `react-native-[android|ios|macos|windows|!linux]`
* use [IndexedDB](https://developer.mozilla.org/fr/docs/Web/API/API_IndexedDB) to store entire library
  * does [pouchdb](https://github.com/pouchdb/pouchdb) would be a better choice ?
    * if I want to add a `sync` (export tracks ?) feature it would be easy af
    * see [RxJS5 + PouchDB — persistent data flows](https://medium.com/@luijar/rxjs-pouchdb-persistent-data-flows-480f503ee41f)
  * look at [Dexie.js](https://github.com/dfahlander/Dexie.js)
* ok, forget `IndexedDB`, use [rxdb](https://github.com/pubkey/rxdb)
  * use by default `pouchdb` and have an adapter for `IndexedDB` if needed
* DON'T FORGET METADATA IN SCHEMA ! (like add time and stuff like this)
* how to handle tracks position in playlist ?
  * to fit YouTube behavior, manual and editable with sync to YouTube playlist
  * or don't, hard and useless feature, just save added date time and allow user to change local whenever he want

## Features
* only **YouTube** playlists
  * does item need to be updated ?
  * do I need to have a specific audio format ? (vorbis, opus, aac ?)
    * but I need to add an `audio` strategy for `epyd` service
  * add/delete/edit features
  * edit song tags (artist/song + easy switch) feature
  * cache feature (update only if changed and not deleted)
* edit playlists cover ?
  * specific app ? - would be fun to work on image generation
* `Search`
  * dissociate (local) library/YouTube
* `Player` (closed)
  * display : cover, song, artist, progress (?)
  * controls : prev, next, play/pause, progress (?)
* `Player` (open)
  * display : cover, song, artist, progress, description (?)
  * controls : video, share (go to YouTube ?), prev, next, play/pause, progress, random, repeat
    * no volume control (only useful for desktop ?)
  * tracklist ? (next tracks)
  * fingers gestures on clear cover
    * tap: pause
    * swipe horizontal: prev/next
    * swipe vertical: volume ?

## Options
* global :
  * hide "defaults" playlists (watch later, history...)
* `Toolbar` "dots" : native action sheet
  * *Order by*
  * `Newly added`
  * `Oldly added`
  * `Artist (A-Z)`
  * `Song (A-Z)`
* `Playlist` "dots": native action sheet
  * `[Clear playlist cache|Cache entire playlist]` (confirm)
  * `Share playlist`
  * `Edit informations`
  * `Delete "Playlist"`
* `Item` "dots" : native action sheet
  * `More "Artist"`
  * `Add to playlist...`
  * `Share track`
  * `Edit informations`
  * `Remove track from playlist`
  * `[Clear track cache|Cache track]` (confirm)
* `Player` "dots" : native action sheet
  * `Add to playlist...`
  * `[Show|Hide] video`
  * `Share track`
  * `Edit informations`
  * `[Clear track cache|Cache track]` (confirm)

## In Progress
* screens
  * home
    * recently added (?)
    * playlist
    * artists
    * library (songs)
  * artist (playlist)
  * search (playlist)
    * differentiate local/youtube items
    * item to search for youtube items (with spinner while loading)
  * options

## Style
* `Player` cover, get colors with [FormidableLabs/image-palette](https://github.com/FormidableLabs/image-palette)
  * specially for `tools` on cover
* `Player` progress shouldn't go to edges : bad UX if user got phone case like mine

## Thanks
* Stocks photos :
  * [Henry Be](https://unsplash.com/photos/bAFiBDMeiVI)
  * [fatman Wong](https://unsplash.com/photos/aSERflF331A)
  * [Feliphe Schiarolli](https://unsplash.com/photos/iWpQdA1e_Uk)
  * [Siddharth Bhogra](https://unsplash.com/photos/k3kdc5MQYyk)
  * [Max Wolfs](https://unsplash.com/photos/yrVv6pwVp78)
  * [Reynier Carl](https://unsplash.com/photos/wf0c0d-h2fE)
  * [Goh Rhy Yan](https://unsplash.com/photos/XgsVB9Uwpq8)
  * [Austin Neill](https://unsplash.com/photos/IfhsSUuzaHc)
  * [Element5 Digital](https://unsplash.com/photos/jCIMcOpFHig)
  * [Fancycrave](https://www.pexels.com/photo/adult-cellphone-day-daylight-583389/)
  * [Leah Kelley](https://www.pexels.com/photo/adult-blur-earphone-guy-325525/)
