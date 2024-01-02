

# 🍿[Google-Drive-Directory-Index](https://github.com/Aicirou/goindex-theme-acrou)
Combining the power of [Cloudflare Workers](https://workers.cloudflare.com/) and [Google Drive](https://www.google.com/drive/) will allow you to index your Google Drive files on the browser.    

[go2index/index.js](https://github.com/Aicirou/goindex-theme-acrou/blob/main/go2index/index.js) is the content of the Workers script.  

This theme's goindex is currently based on [yanzai/goindex](https://github.com/yanzai/goindex/).
## Demo  

🚀 Go to: [https://chill.aicirou.workers.dev/](https://chill.aicirou.workers.dev/) 

🛠 Quick Development: [here/](https://github.com/Aicirou/goindex-theme-acrou/edit/main/README.md#quick-deployment)

## ✨Features

- [x] 👑 Page-level caching,browser forward and backward without reloading (MAC users have a better experience with the trackpad)
- [x] 🗂 Multi drive switching
- [x] 🔐 Http Basic Auth
- [x] 🎨 Grid view mode(File Preview)
- [x] 🎯 Paging load
- [x] 🌐 I18n(multi-language)
- [x] 🛠 Markdown/Html render (Maybe it can be your blog)
- [x] 🖥 Video Online(.vtt subtitle)
- [x] 🕹 Support for custom video player (API)
- [x] 🎧 Audio Online
- [x] 🚀 Faster speed

## TODO

- [ ] More file format preview
- [ ] Let goindex be more than just a directory index

## Quick Deployment

1. Open the following link

- https://goindex-builder-acrou.glitch.me

2. Auth and get the code
3. Deploy the code to [Cloudflare Workers](https://www.cloudflare.com/)

## Manual Deployment  

1. Open [Google Drive API](https://console.developers.google.com/apis/api/drive.googleapis.com/overview)
2. Create a [OAuth client ID](https://console.developers.google.com/apis/credentials/oauthclient)
3. Install [rclone](https://rclone.org/downloads/) software locally
4. Get `refresh_token ` with `rclone`
5. Download `index.js` in https://github.com/Aicirou/goindex-theme-acrou/tree/master/go2index and replace `client_id`,`client_secret`,`refresh_token` for what you just got.
6. Deploy the code to [Cloudflare Workers](https://www.cloudflare.com/)

## Options

### Video

| Option       | Type                       | Default                                                      | Description                                                  |
| ------------ | -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `api`        | String                     | `''`                                                         | External video player api. When this value is not null, all of the following options do not work |
| `autoplay`   | Boolean                    | `true`                                                       | When set to true, the video plays automatically, depending on whether the browser supports the |
| `invertTime` | Boolean                    | `false`                                                      | Display the current time as a countdown rather than an incremental counter. |
| `controls`   | Array, Function or Element | `['play-large', 'restart', 'play', 'progress', 'current-time', 'duration', 'mute', 'volume', 'captions', 'settings', 'pip', 'airplay', 'download', 'fullscreen']` | Which buttons are displayed in the control bar. See more [CONTROLS.md](https://github.com/sampotts/plyr/blob/master/CONTROLS.md#using-default-controls) |
| `settings`   | Array                      | `['quality', 'speed', 'loop']`                               | You can specify which settings to show in the menu           |

For more option, see plyr [options](https://github.com/sampotts/plyr#options)

### Audio

| Option      | Type    | Default    | Description                                                  |
| ----------- | ------- | ---------- | ------------------------------------------------------------ |
| `container` | String  | `.aplayer` | No support for changes                                       |
| `fixed`     | Boolean | `true`     | No support for changes                                       |
| `autoplay`  | Boolean | `false`    | audio autoplay                                               |
| `loop`      | String  | `'all'`    | player loop play, values: 'all', 'one', 'none'               |
| `order`     | String  | `'list'`   | player play order, values: 'list', 'random'                  |
| `preload`   | String  | `'auto'`   | values: 'none', 'metadata', 'auto'                           |
| `volume`    | Number  | `0.7`      | default volume, notice that player will remember user setting, default volume will not work after user set volume themselves |
| `audios`    | Array   | `[]`       | Playlists can be preset. [FAQ](#FAQ)                         |

For more option, see APlayer [options](https://aplayer.js.org/#/home?id=options)

## Change log

### v2.0.8

- Fix image file actions does not work
- Fix misjudged file to image format
- Fix more than 10 drive not working
- Fix some of the operation functions in the search list cannot be used
- Fix text cache content not refreshing
- Add video default player([plyr](https://github.com/sampotts/plyr))
- Add audio player ([APlayer](https://github.com/MoePlayer/APlayer)) 
- Add copy button to video page
- Add [NProgress](https://github.com/rstacruz/nprogress)
- Add language cache cleanup
- Add shortcut can't download tip
- Markdown displays rendered html by default
- CLI Delete prefetch preload of lazy load module
- Delete fontawesome5

### Fixed issues

- Add clean file cache
- Support for custom video player (API)
- Beautify: the grid mode file shows icon when no preview is shown
- Beautify: Adjust the HEAD.md render position
- Solve the problem that files that can't be previewed can't be downloaded directly by clicking
- Solve the problem that the file name cannot be opened
- Solve the problem that switching pages will fall back in the current page loading

- Program changed to SPA(single page application)
- Add page level cache(Browser forward and backward do not refresh seconds to load, and Mac users have a better experience of using touch pad)
- Add http basic auth(Each drive letter can be configured with a user name and password separately, which can protect all sub files and sub folders under the drive)
- Add  grid view mode(File preview)
- Add paging load
- Add  i18n
- Add html render 
- Add render folder/file description
- Add optional configuration
- Support quick deployment
- Support PDF Online preview
- Replace text editor
- Solve the problem of URL encoding
- Solve other known problems

- Support multi disk switching
- Add version detection
- Optimize search results
- Optimize page display

## License

[MIT](LICENSE)

