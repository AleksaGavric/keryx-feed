# Keryx Podcast Feed

The RSS publishing repository for **Keryx**, an AI and technology news podcast with Aleksa and Juno. This repository contains feed metadata, not the audio-generation or editorial pipeline.

## Subscribe

[RSS feed](https://aleksagavric.github.io/keryx-feed/feed.xml)

Paste the feed URL into a podcast app that supports adding a show by URL. Audio and cover artwork are hosted separately on Muse's podcast CDN.

## Repository contents

- `feed.xml` — channel metadata and published episode entries.
- `README.md` — feed scope and local validation instructions.

An external publishing workflow updates the feed; its implementation is not included here. Publication cadence and CDN availability depend on that separate system.

## Validate XML locally

```sh
python3 -c 'import xml.etree.ElementTree as ET; root = ET.parse("feed.xml").getroot(); assert root.tag == "rss"; assert root.find("channel") is not None; print("RSS XML parsed")'
```

This checks XML structure, not complete podcast-platform compliance or remote enclosure availability. Keep existing episode GUIDs stable when editing entries to avoid duplicate downloads for subscribers.
