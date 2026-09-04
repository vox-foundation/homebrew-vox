# Homebrew tap for Vox

```bash
brew tap vox-foundation/vox
brew install vox
```

## Why install this way on macOS

`brew` fetches over curl, and curl does not set `com.apple.quarantine` —
LaunchServices applies that on behalf of browsers. A tarball downloaded from the
GitHub Releases *page* in a browser **is** quarantined, and because the macOS
binaries are ad-hoc (linker) signed rather than notarized, macOS kills them with
no useful message. Installing through this tap avoids that path entirely.

`curl https://voxlang.org/voxup | sh` is unaffected for the same reason, and
remains the other supported path.

## Maintaining the formula

`Formula/vox.rb` is generated from a release's `checksums.txt`. The `version`,
both `url`s and both `sha256`s are pinned to one release and go stale the moment
another ships — they must be rewritten per release, not hand-edited.

The canonical copy lives in the main repo at `Formula/vox.rb`
(`vox-foundation/vox`); this tap is a publishing target for it.
