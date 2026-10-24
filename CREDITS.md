# Bear+ review demo playlist

`bearplus-demo.m3u` lets Google Play reviewers sign in to Bear+ and try Live TV, Movies and Series without anyone's paid IPTV account. It holds only public-domain works, Creative Commons films (shared unchanged, credited below) and public test streams. It is not hosted anywhere yet.

- **Live TV (3):** two real live test signals from Unified Streaming's public demo, and one official NASA+ video (on-demand HLS: Bear+ lists every `.m3u8` link under Live TV).
- **Movies (13):** 6 Blender open films, 5 public-domain classics, 2 NASA Apollo films.
- **Series (2 shows, 8 episodes):** Caminandes (Blender, 3 episodes) and NASA's Apollo Digest (5 episodes).

Each entry follows Bear+'s M3U rules (`M3uPlaylist.kt`): `.m3u8` links become channels, `.mp4`/`.mov`/`.webm` links become movies, and a title with `S01 E02` makes an episode of the show named before it. The playlist sets `tvg-logo` and `group-title` on every entry and gives no guide (`url-tvg`).

## What's in it

All links checked on 2026-10-24 from a Mac: a ranged `curl` GET (200/206 and a video or HLS content type; for HLS, the master playlist lists variants and the first variant lists segments), `ffprobe` for codecs, and a full GET of every image (200, `image/*`). No link redirects.

| # | Title | Group in Bear+ | Source | Licence / rights basis and credit | Checked 2026-10-24 |
|---|---|---|---|---|---|
| 1 | Live Test Signal (Unified Streaming) | Live · Test Signals | [source](https://demo.unified-streaming.com/k8s/live/stable/) | Public demo live stream offered by Unified Streaming for player testing; content is a machine-generated test pattern (colour bars + clock). No licence text published. Credit: Stream: Unified Streaming demo (demo.unified-streaming.com). Channel icon: SMPTE colour bars, Wikimedia Commons, public domain. | OK: 200 application/vnd.apple.mpegurl, 2 variants, live; h264 1280x720/aac; image 200 image/png |
| 2 | Low-Latency Test Signal (Unified Streaming) | Live · Test Signals | [source](https://demo.unified-streaming.com/k8s/low-latency/stable/) | Public demo live stream offered by Unified Streaming for player testing; machine-generated test pattern (colour bars + clock). No licence text published. Credit: Stream: Unified Streaming demo (demo.unified-streaming.com). | OK: 200 application/vnd.apple.mpegurl, 2 variants, live; aac/h264 640x360/h264 1280x720; image 200 image/png |
| 3 | NASA+ · Artemis II: Meet the Astronauts | Live · NASA+ (on demand) | [source](https://plus.nasa.gov/video/artemis-ii-meet-the-astronauts-who-will-fly-around-the-moon-official-nasa-video/) | Official NASA video on NASA's own HLS host (NASA+). US federal government work, used under the NASA Media Usage Guidelines. On-demand HLS: Bear+ lists every .m3u8 link under Live TV. Credit: Video: NASA (plus.nasa.gov). | OK: 200 application/x-mpegURL, 9 variants, on-demand; aac/mjpeg 480x320/h264 416x234/h264 480x270/h264 640x360/h264 960x540/h264 1280x720/h264 1920x1080; 3:09; image 200 image/jpeg |
| 4 | Tears of Steel (2012) | Movies · Open Films | [source](https://studio.blender.org/projects/tears-of-steel/) | CC BY 3.0 (film). Soundtrack files are CC BY-ND 3.0 (Joram Letwory); the film is shared unchanged. Credit: (CC) Blender Foundation \| mango.blender.org | OK: 206 video/quicktime; h264 1280x534/mp3; 12:14; image 200 image/png |
| 5 | Elephants Dream (2006) | Movies · Open Films | [source](https://studio.blender.org/projects/elephants-dream/) | CC BY 2.5 Credit: (c) 2006 Blender Foundation / Netherlands Media Art Institute \| orange.blender.org | OK: 206 video/quicktime; h264 1024x576/aac; 10:58; image 200 image/jpeg |
| 6 | Big Buck Bunny (2008) | Movies · Open Films | [source](https://commons.wikimedia.org/wiki/File:Big_Buck_Bunny_4K.webm) | CC BY 3.0 Credit: (c) copyright 2008, Blender Foundation \| www.bigbuckbunny.org | OK: 206 video/webm; vp9 1920x1080/opus; 10:34; image 200 image/jpeg |
| 7 | Sintel (2010) | Movies · Open Films | [source](https://commons.wikimedia.org/wiki/File:Sintel_movie_4K.webm) | CC BY 3.0 Credit: (c) copyright Blender Foundation \| durian.blender.org | OK: 206 video/webm; vp9 1920x818/opus; 14:48; image 200 image/jpeg |
| 8 | Spring (2019) | Movies · Open Films | [source](https://commons.wikimedia.org/wiki/File:Spring_-_Blender_Open_Movie.webm) | CC BY 4.0 Credit: Andy Goralczyk / Blender Foundation \| studio.blender.org/films/spring | OK: 206 video/webm; vp9 2048x858/opus; 7:44; image 200 image/jpeg |
| 9 | Coffee Run (2020) | Movies · Open Films | [source](https://commons.wikimedia.org/wiki/File:Coffee_Run_-_Blender_Open_Movie-full_movie.webm) | CC BY 4.0 Credit: Blender Studio / Blender Foundation \| studio.blender.org | OK: 206 video/webm; vp9 1920x804/opus; 3:04; image 200 image/png |
| 10 | A Trip to the Moon (1902) | Movies · Classics | [source](https://commons.wikimedia.org/wiki/File:Le_Voyage_dans_la_Lune_%281902%29.webm) | Public domain (1902; Georges Méliès died 1938). Silent, no added music track. Credit: Georges Méliès | OK: 206 video/webm; vp9 1440x1080; 12:46; image 200 image/jpeg |
| 11 | The Great Train Robbery (1903) | Movies · Classics | [source](https://commons.wikimedia.org/wiki/File:The_Great_Train_Robbery_%281903%29.webm) | Public domain (1903, Edison; copy from the Library of Congress). Silent, no added music track. Credit: Edwin S. Porter / Edison Manufacturing Co. | OK: 206 video/webm; vp9 1440x1080; 13:27; image 200 image/jpeg |
| 12 | Sherlock Jr. (1924) | Movies · Classics | [source](https://commons.wikimedia.org/wiki/File:Sherlock_Jr._%281924%29.webm) | Public domain in the US (published 1924). Silent, no added music track. Credit: Buster Keaton | OK: 206 video/webm; vp9 1440x1080; 44:05; image 200 image/jpeg |
| 13 | The General (1926) | Movies · Classics | [source](https://commons.wikimedia.org/wiki/File:The_General_%281926%29.webm) | Public domain in the US (published 1926). Silent, no added music track. Credit: Buster Keaton, Clyde Bruckman | OK: 206 video/webm; vp9 1440x1080; 1:15:51; image 200 image/png |
| 14 | His Girl Friday (1940) | Movies · Classics | [source](https://commons.wikimedia.org/wiki/File:His_Girl_Friday_%281940%29_by_Howard_Hawks.webm) | Public domain in the US: copyright not renewed (Commons tag PD-US-not renewed); the source play The Front Page (1928) is also public domain in the US. Credit: Howard Hawks / Columbia Pictures | OK: 206 video/webm; vp9 1440x1080/opus; 1:31:54; image 200 image/jpeg |
| 15 | Eagle Has Landed: The Flight of Apollo 11 (1969) | Movies · NASA | [source](https://images.nasa.gov/details/KSC-19690716-MH-NAS01-0001-The_Flight_of_Apollo_11_The_Eagle_Has_Landed_HS_from_Film_JSC-DVC_1928) | NASA film HQ-194 (1969), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; h264 720x486/aac; 46:59; image 200 image/jpeg |
| 16 | Apollo 12: Pinpoint for Science (1969) | Movies · NASA | [source](https://images.nasa.gov/details/KSC-1969-MH-NAS01-0001-Apollo_12_Pinpoint_for_Science-B_425) | NASA film HQ-197 (1969), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1280x720; 28:39; image 200 image/jpeg |
| 17 | Caminandes S01 E01 · Llama Drama (2013) | Series · Caminandes | [source](https://commons.wikimedia.org/wiki/File:Caminandes-_Llama_Drama_-_Short_Movie.ogv) | CC BY 3.0 Credit: Pablo Vazquez, Beorn Leonard, Francesco Siddi; music and sound Jan Morgenstern \| caminandes.com | OK: 206 video/webm; vp9 1920x1080/opus; 1:29; image 200 image/jpeg |
| 18 | Caminandes S01 E02 · Gran Dillama (2013) | Series · Caminandes | [source](https://commons.wikimedia.org/wiki/File:Caminandes,_Gran_Dillama_-_Blender_Foundation.webm) | CC BY-SA 3.0 (as listed on Commons): may be shared unchanged with credit. Credit: Blender Institute: Pablo Vazquez, Beorn Leonard, Francesco Siddi; soundtrack Jan Morgenstern | OK: 206 video/webm; vp8 1920x1080/vorbis; 2:26; image 200 image/jpeg |
| 19 | Caminandes S01 E03 · Llamigos (2016) | Series · Caminandes | [source](https://commons.wikimedia.org/wiki/File:Caminandes_3_-_Llamigos_-_Blender_Animated_Short.webm) | CC BY 3.0 Credit: Blender Institute; music Torin Borrowdale, sound Sander Houtman | OK: 206 video/webm; vp8 1920x1080/vorbis; 2:30; image 200 image/jpeg |
| 20 | Apollo Digest S01 E01 · Testing Apollo | Series · Apollo Digest (NASA) | [source](https://images.nasa.gov/details/NDTV000907_Apollo_Digest_Series_Testing_Apollo) | 1960s NASA film series (NASA Armstrong archive), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1920x1080; 5:28; image 200 image/jpeg |
| 21 | Apollo Digest S01 E02 · Spacecraft for Apollo | Series · Apollo Digest (NASA) | [source](https://images.nasa.gov/details/NDTV000908_Apollo_Digest_Series_Spacecraft%20for%20Apollo) | 1960s NASA film series (NASA Armstrong archive), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1920x1080; 4:41; image 200 image/jpeg |
| 22 | Apollo Digest S01 E03 · Saturn Third Stage | Series · Apollo Digest (NASA) | [source](https://images.nasa.gov/details/NDTV000909_Apollo_Digest_Series_SATURN_THIRD_STAGE) | 1960s NASA film series (NASA Armstrong archive), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1920x1080; 5:38; image 200 image/jpeg |
| 23 | Apollo Digest S01 E04 · Mission Control | Series · Apollo Digest (NASA) | [source](https://images.nasa.gov/details/NDTV000910_Apollo_Digest_Series_Mission_Control) | 1960s NASA film series (NASA Armstrong archive), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1920x1080; 5:29; image 200 image/jpeg |
| 24 | Apollo Digest S01 E05 · The Lunar Module | Series · Apollo Digest (NASA) | [source](https://images.nasa.gov/details/NDTV000948_Apollo_Digest_Series_The_Lunar_Module) | 1960s NASA film series (NASA Armstrong archive), US federal government work: public domain in the US (NASA Media Usage Guidelines). Credit: NASA | OK: 206 video/mp4; aac/h264 1920x1080; 5:21; image 200 image/jpeg |

Notes:
- **NASA live:** NASA phased out its 24/7 NASA TV broadcast in 2024. The old NASA TV HLS master playlists (`ntv1`/`ntv2.akamaized.net`) still answer, but their variant playlists return 404, so they are left out. nasa.gov/live now embeds YouTube, and I found no public NASA live HLS link.
- **Test signals:** the two Unified Streaming streams are a public demo for testing players: colour bars, a clock and the company's logo. They carry no third-party content, but no licence text is published for them.
- **Formats:** the Blender and NASA files are H.264/AAC (MP4/MOV). Tears of Steel has MP3 audio inside its MOV file. The Wikimedia Commons files are WebM: VP9/Opus, or VP8/Vorbis for Caminandes 2 and 3. Bear+'s player (Media3/ExoPlayer) supports both, but none of this has been played on a TV yet, so open one item from each tab before submitting.
- **Hosts:** NASA (images-assets.nasa.gov, nasaplus.akamaized.net), Blender (download.blender.org), Wikimedia Commons (upload/thumb.wikimedia.org) and Unified Streaming. The Internet Archive was left out because it served about 10 KB/s from here, which is too slow to play. Repeated checks from one IP got HTTP 429 from Wikimedia (retry after 10 minutes), so don't mass-check these links. One viewer playing one film makes only a few requests.
- **Posters and icons** come from the same sources: Commons posters (CC BY for the Blender films, public domain for the classics), Commons video frames, NASA video frames, and a public-domain colour-bars image for the test signals.
- **NASA:** no NASA logo or insignia is used, and nothing suggests NASA endorses Bear+ (NASA Media Usage Guidelines: https://www.nasa.gov/nasa-brand-center/images-and-media/).
- **Public domain is judged for the US.** Some classics (the Keaton films, His Girl Friday) may still be under copyright in some other countries.

## Hosting the file

Bear+ downloads the link with a plain GET: no login, no cookies, no redirect to a sign-in page. It needs a 200 response whose text starts with `#EXTM3U`. The content type doesn't matter. Reviewers type the link with a TV remote, so keep it short.

1. **GitHub Pages:** make a new public repo (for example `bearplus-demo`), add `bearplus-demo.m3u` and turn on Pages. The link is `https://<user>.github.io/bearplus-demo/bearplus-demo.m3u`. A custom short domain also works.
2. **Raw file in a public repo:** `https://raw.githubusercontent.com/<user>/<repo>/main/bearplus-demo.m3u`. The Bear+ app repo may be private, and raw links from a private repo need a token, so use a separate public repo.
3. **GitHub Gist (public or secret):** use the raw link without a commit hash, `https://gist.githubusercontent.com/<user>/<gist-id>/raw/bearplus-demo.m3u`, so later edits keep the same link. The link is long to type.
4. **Any static host** (Cloudflare Pages, Netlify, your own site).

After hosting, open the link in a browser (the text should show), then sign in once on a TV or emulator. Bear+ keeps a copy and refreshes it every 6 hours.

## Play Console: App content > App access

Choose **"All or some functionality is restricted"** and add one set of instructions:

- **Name:** Demo playlist (no account needed)
- **Username / Password:** not needed (if the form insists, enter `not needed`)
- **Any other information:** paste the text below, with the real link filled in.

```
Bear+ is a player for the user's own IPTV service. For review, use this free demo playlist. It contains only public-domain and Creative Commons videos and public test streams. No account, subscription or payment is needed.

1. Open Bear+. On the sign-in screen, choose "Use the remote instead".
2. In "Server address or playlist link", replace "http://" with:
   https://YOUR-HOST/bearplus-demo.m3u
3. Leave "Username" and "Password" empty and choose "Continue".

Live TV, Movies and Series then fill from the playlist. Live TV has two live test signals and a NASA video. Movies has Blender open films, public-domain classics and NASA Apollo films. Series has Caminandes and NASA's Apollo Digest.
Alternative: on the first sign-in screen, scan the code with a phone on the same Wi-Fi and paste the same link there, leaving username and password empty.
```
