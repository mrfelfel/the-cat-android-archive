# The Cat

**A people's messenger — familiar by design, independent by nature.**

The Cat is a complete messenger: a Telegram-grade Android client and a secure,
independently-operated backend rebuilt from the MTProto protocol up. Not a demo.
Not a partial fork sold by the kilo. A whole product, built to be trusted.

> Built on **MTProto API layer 230**, on the shoulders of
> [Telegram for Android](https://github.com/DrKLO/Telegram) `v12.10.1`.

## The server — ours, and we guarantee it

The Cat runs on our own server infrastructure. It is **not** open for anyone to
host, and it does not need to be: we operate it, we harden it, and we stand
behind its security. What we open is the code that runs on *your* device — the
client — so that the part you can read is the part that lives in your pocket.

| | |
|---|---|
| Host | `62.220.127.238` |
| Port | `30001` |
| Transport | MTProto, RSA-pinned below |

The client pins the server's RSA key below. This is a **public** key — it is
what lets your app talk to our server securely, and it is embedded in every
build we ship. (What stays out of this repo is the app's *signing* key, which
only we hold and which never leaves our release machine.)

```
-----BEGIN RSA PUBLIC KEY-----
MIIBCgKCAQEA2LnOaBr+GoK84cDv4c0h3cLZ2EAJsnI+syy7L7VdFV9JkHQ3ODA8
ydSND5DfmDp7ZMG5AQWu+ca9jrRNqgiHtmTdLcZfLM/2XXEqYznNfikpmelv0qA3
UvNdDTD24PVwXpMwe86j+On45NgZcvS464DUGcM2wPDY0zOIFInVL+R3u+XmIJ8E
FxdZxR+4ktDx6Pb+OoxmpH4Y9KHbLNwQ7MmFSW9Luw7z02D2ySD3edQIrdeXI6pW
aNOZhRIKfL94qJbdG0+7fUp0M7d2WjKKoyZ2Vb1Yt6BDUqr+pG/6/lJOL4p4EKEg
MwitjfUc+a9fPtKx25osD33c0L5889yVkQIDAQAB
-----END RSA PUBLIC KEY-----
```

## Why it exists

Networks fail. They are switched off, throttled, and partitioned — and the
people who depend on them are the last to be told. The Cat grew out of years of
writing about exactly that risk, and out of a stubborn belief that a messenger
worth trusting should be one whose maker is accountable for it: operated on
infrastructure built to keep running, and honest about the code it puts on your
device.

That is the whole ambition: **a messenger that answers to its users, not to a
network that can be turned off.**

## The maker

The Cat is built by **Felfel** — Mohammad Javad Yahyahi — together with the team
at **Shalgham** (data processing) and its parent company **Sefr ta Sad**.

For years, Felfel wrote about a danger most people never see coming: networks
that can be switched off, and the millions left suddenly unable to reach each
other. The Cat began in the middle of that work — first as a small messenger
built on plain web tech and a Go backend, then, after seeing that people are
simply more comfortable inside an interface they already know, as a serious
attempt to build a real one.

That path ran from studying and reverse-engineering the MTProto protocol, through
a year of building a backend that could actually scale, to syncing the Android
client up to layer 230 — with a lot of patient help from Claude Code along the
way. Not a hobby fork. Not a shortcut. A people's messenger, built to be here.

## Built on Telegram. Not a knockoff.

We stand on Telegram's protocol and its Android client, and we say so plainly.
Telegram published its clients under the **GNU GPL**; honoring that license is
not a burden, it is the point. Our changes — the client, the rebrand, the
layer-230 sync work — are open, in this repository, under the same terms.

Some forks quietly hide their lineage. We would rather be honest about it. A
clone done right is what Brave is to Chromium: unmistakably its own product,
proud of its identity, and completely open about what it stands on.

## What's inside

- **A real backend.** The server is engineered from the MTProto ground up:
  clustering on Kubernetes, multi-service and edge deployment, and an
  architecture built to scale horizontally — operated by us, end to end.
- **The interface people already know.** The Cat keeps the Telegram client
  surface that users are already fluent in, so there is nothing new to learn and
  nothing familiar to lose.
- **Layer 230, synced deep.** We wrote and synchronized the Android client up to
  **API layer 230**, bringing the client to roughly **90% feature parity** with
  the stock experience.
- **One trusted server.** The Cat ships against our server by default — no
  address to type, no key to paste. Install, sign in, and go.

## Security through transparency

We split the trust deliberately:

- **The client is open.** It runs on your device, so it is the code that matters
  most to read. Every line is here. Don't trust our binary? Build it from source
  and run the APK you compiled.
- **The server is ours.** It runs on our infrastructure, closed and hardened,
  and its security is our responsibility — one we guarantee.

A messenger you cannot read is a messenger you cannot verify. So we open the
half you can hold, and we own the half we operate.

## Getting started

**Requirements:** JDK 17+, Android SDK (compile/target API 36, build-tools
36.0.0, NDK 27.2.12479018), Git. Minimum device API is 21 (Android 5.0).

```bash
git clone <this-repo>
cd thecat-android
./gradlew assembleRelease
```

On Windows, `build-android.bat` walks you through API credentials, SDK and
Gradle interactively, and remembers your answers in a gitignored local file.

For release signing and per-channel builds, see the scripts under `scripts/`.

## License

The Cat is free and open-source software, licensed under
**GNU GPL v2 or later** — see [LICENSE](LICENSE).

Based on [Telegram for Android](https://github.com/DrKLO/Telegram), © Telegram
Messenger LLP, used and redistributed in accordance with the GPL.

---

*The Cat — because a messenger should belong to the people who use it.*
