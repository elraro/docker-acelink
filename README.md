# docker-acelink

Based on the original project by @blaise-io

Play an Acestream or Magnet in any media player by running Acestream in Docker, or using the web player.

Requires Docker


### Media players

Ace Link allows selecting your own media player. Ace Link does not transcode streams, so pick a player that supports popular audio and video codecs. VLC, IINA and MPV are free and open source media players that are able to play nearly anything. QuickTime and web browsers will play most streams, but not all. 

### Ace Stream server only

Running the Acestream Engine:

```sh
docker run --platform=linux/amd64 --rm -p 6878:6878 ghcr.io/tr4il/acelink
# now open http://<network ip>:6878/ace/getstream?id=<acestream id>
# or http://<network ip>:6878/ace/getstream?infohash=<magnet uri> in a player
# or access at http://127.0.0.1:6878/webui/player/<acestream id> in a webbrowser
```

If you want to use a custom acestream.conf: 
```
docker run --platform=linux/amd64 --rm -p 6878:6878 -v "$(pwd)/acestream.conf:/opt/acestream/acestream.conf" ghcr.io/tr4il/acelink
```
