# r/chess pgn viewer

View pgn boards inline on r/chess. 
Current version: 1.94.0

## Installation

[Link on chrome webstore](https://chrome.google.com/webstore/detail/reddit-pgn-viewer/hplecpnihkigeaiobbmfnfblepiadjdh?hl=en)

[Link on firefox add-on](https://addons.mozilla.org/en-us/firefox/addon/rchess-pgn-viewer/)

## Contributing

Chrome extension files in chrome folder, firefox in ffox folder. We really only care about two files, rchesspgn.js and rchess.css. They should be identical in both the chrome and ffox folders.

### Requirements

1. npm
2. chrome. firefox.

### Setup

1. Clone repo to get local files.
2. `npm install`
3. [Instructions](https://developer.chrome.com/extensions/getstarted#unpacked) for setting up chrome extension development locally.

### Making changes

##### For chrome

After every change, reload the extension from the extensions menu in chrome (`chrome://extensions/`).

##### For firefox

After every change, run `jpm run` from the ffox folder. This should launch a new firefox instance with your latest changes.

### Packaging

##### For chrome

1. Bump up version number in manifest
2. Zip chrome folder.
3. Upload zip file at chrome developer dashboard.

##### For firefox

1. Bump up version number in package.json
2. run `jpm xpi` in the ffox folder.
3. Upload at firefox add-on developer hub.

## TODO

* Show/copy/download pgn.

* Show more metadata. Maybe put it in something that can be toggled that defaults to hidden.
  ```
  this.showEvent=1;
  this.showRound=1;
  this.showSite=1;
  this.showDate=1;
  ```

* Play out on board - we could export fen to lichess analysis board. Sample url:
    `http://en.lichess.org/analysis/r3kb1r/pp1n1ppp/3pn3/Q1pN4/8/2P5/PP3PPP/R3K1NR_w_KQkq_-_1_12?color=white`

* Expose the option object to pass to the viewer so people can costumize the board.

* Multiple boards in one post - this is supported by putting them all in one tag, but multiple tags seems to be more intuitive to people. There's unfortunately currently a bug with using multiple pgn tags in one post. Only the last board's controls work.

* [fen]position[fen] instead of [pgn][fen position][/pgn] seems more intuitive to people.

* Puzzle mode. Hide the move text until toggled to show.

* A reddit bot to post fen image/link to external pgn viewer when seeing fen/pgn tags.

  This is the best thing I can think of to help people without the viewer, but I don't like that FEN would require people to have RES in order to view inline, and pgn would't be inline since it'd be to an external viewer. We might want to hit up the guy who made the pgn viewer bot so we don't end up with multiple bots in the subreddit.

* Other browsers?

* Automate the packaging process for chrome/firefox using grunt

* Instead of handling reddit's markdown gorking the pgn text, grab the source for the comment from reddit instead.

* There's sometimes no brackets around the ratings. See coloradosherrif test 01/06/13. You can also trigger by switching games back and forth in multi game posts. I think that's part of the pgnviewer code. Might want to just use a space instead.

## License

MIT
