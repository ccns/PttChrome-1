# PttChrome-CCNS

[![build and deploy status](https://github.com/ccns/PttChrome/actions/workflows/deploy-ghpage.yml/badge.svg)](https://github.com/ccns/PttChrome/actions/workflows/deploy-ghpage.yml)

A Telnet-over-WebSocket client, forked from [robertabcd/PttChrome](https://github.com/robertabcd/PttChrome).

To quickly grasp the idea of how to customize the behavior, see [.github/workflows/deploy-ghpage.yml](.github/workflows/deploy-ghpage.yml).

This workflow sets up the configuration before building PttChrome. The client built with this configuration connects to DreamBBS ([ccns.cc](https://term.ccns.cc)) by default and uses the icon set provided by CCNS.

Without such configuration, the built client will instead connect to Ptt ([ptt.cc](https://term.ptt.cc)) and use the icon set from the original PttChrome as the original version does.

## How to Contribute

If you want to fix something or add general features, please also consider the upstreams:
+ v2 (WebSocket support, etc.): [robertabcd/PttChrome](https://github.com/robertabcd/PttChrome)
+ v1 (user interface, etc.): [iamchucky/PttChrome](https://github.com/iamchucky/PttChrome)

## Version Information

A semver-like versioning scheme has been employed. See https://github.com/ccns/PttChrome/tags for the list of version tags.

### Major version

- v1: A web page requiring browser extension (Google Chrome–only)
    - Main repo: [iamchucky/PttChrome](https://github.com/iamchucky/PttChrome)
    - v1 is developed on two branches:
        - `gh-pages` (the web page part; the "webapp" branch)
            - The branch was abandoned in v2 but is reused by CCNS's fork
        - `master` (the browser extension part)
            - `master` now also includes a refactored version of `gh-pages`
    - `gh-pages` became independent of `master` after v0.0.5
- v2: A standalone web page (with cross-browser support)
    - Main repo: [robertabcd/PttChrome](https://github.com/robertabcd/PttChrome)
    - v2 is developed on the branch `dev` (formerly on `gh-pages`)
        - `dev` was forked from `gh-pages` in 2017

### Minor/Patch Version

#### v1

In v1, since version bumps was done rather regularly, the version tag is retrospectively assigned accordingly:
- `master`
    * All version-bumping commits are tagged.
- `gh-pages`
    * All version-bumping commits are tagged.
    * The latest commit made before a version-bumping commit on `master` is tagged with the bumped version number plus the "webapp" version.

#### v2

In v2, due to the lack of version bumps before, a way for determining the version number retrospectively is needed.

Every merge commit not followed by a version-bumping commit are tagged, with the increased version field determined as follow:
- Minor: After the last tag, there are any ancestor commits containing `feat` in the title.
- Patch: Otherwise.

### About This Branch

This branch `main-ccns.2021` was rebased onto `dev` in 2021 and is maintained by CCNS.

Versions tagged on this branch have the `-ccns.2021` suffix.
