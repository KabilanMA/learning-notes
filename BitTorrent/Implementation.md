## Finding peers
- BitTorrent is not entirely decentralized. We need centralized servers that introduce peers to each other. They are just web servers running over *HTTP*.
- But there are new methods like **DHT**, **PEX**, and **magnet links**, which cuts out the middleman by making even **peer discovery** a distributed process.

## Parsing a .torrent file
- A .torrent file descibes the contents of a torrentable fie and information for connecting to a tracker.
- .torrent files is in encoded format called **[[General#Bencode|B-encode]]** and we need to decode it.
[Link](https://blog.jse.li/posts/torrent/#parsing-a-torrent-file)

Prettier format of a .torrent file:

```YAML
d
  8:announce
    41:http://bttracker.debian.org:6969/announce
  7:comment
    35:"Debian CD from cdimage.debian.org"
  13:creation date
    i1573903810e
  4:info
    d
      6:length
        i351272960e
      4:name
        31:debian-10.2.0-amd64-netinst.iso
      12:piece length
        i262144e
      6:pieces
        26800:�����PS�^�� (binary blob of the hashes of each piece)
```

In this file, we can spot the URL of the tracker, the creation date (as a Unix timestamp), the name and size of the file, and a big binary blob containing the [[General#SHA-1 Hashing|SHA-1]] hashes of each piece, which are equally-sized parts of the file we want to download.

The exact size of a piece varies between torrents, but they are usually somewhere between 256 KiB and 1 MiB. (This mean a large file is made of thousands of pieces)

We'll download these pieces from our peers, check them against the hashes from our torrent file, assemble them together, and get the full file.

This mechanism allows us to verify the integrity of each piece as we go. It makes BitTorrent resistant to accidental corruption and intentional [[Terminologies#Torrent poisoning|torrent poisoning]].
Unless an attacker is capable of breaking SHA-1 with a [[Terminologies#Preimage attack|preimage attack]], asked content will be delivered with no problem.
