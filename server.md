# Server Discussion

This document is intended to document many of the deep thoughts and
considerations that are day-to-day in server administration. I think it is
increasingly important to document my experiences with distros and software in
general. I have a tendency to jump between software stacks just to learn new
material, but now I can more formally document which software is the best for me.

<!-- vim-markdown-toc GFM -->

- [Disto Battles](#disto-battles)
  - [Fedora](#fedora)
    - [Pros](#pros)
    - [Cons](#cons)
  - [Debian](#debian)
    - [Pros](#pros-1)
    - [Cons](#cons-1)
- [Containerization](#containerization)
  - [Docker](#docker)
    - [Pros](#pros-2)
    - [Cons](#cons-2)
  - [Podman](#podman)
    - [Pros](#pros-3)
    - [Cons](#cons-3)

<!-- vim-markdown-toc -->

## Disto Battles

Which server distro is best? Of course, all Linux. What's better than Linux?

### Fedora

#### Pros

- Bleeding edge software - very rarely am I missing any software that I require.
- FirewallD is an absolute godsend of a firewall management system.
- `dnf` is wonderful, fast, and **simple**.
- Lightweight with sensible defaults.
- SELinux enabled by default.
- Newer kernel, 5.9.

#### Cons

- There are too many updates! While this sounds like a superficial issue, too
  many unstable updates cause lots of issues. Docker daemon tends to break
  whenever updating the system leading to service interruptions. When
  possible; either don't update the system or do so exhibiting extreme
  caution.
- Nginx / LetsEncrypt / CertBot experience sucks, no other way to say it. I wish
  this could be dockerized. File locations are frequently different from Debian
  based systems (for some reason?).
- More frequent kernel upgrades.

### Debian

#### Pros

- Incredibly stable, software is thoroughly tested before being released into
  apt.
- Basically everything is supported on some Debian based distro whether that be
  Ubuntu or stock Debian, although it is important to remember to never mix
  PPAs.
- Lightweight, with a little less, but still sensible defaults.
- More sysadmin oriented community.
- Less frequent kernel upgrades.

#### Cons

- Software is frequently out-of-date and often is missing the latest features.
- No SELinux by default.
- Older kernel, 4.19.

## Containerization

### Docker

#### Pros

TODO

#### Cons

TODO

### Podman

#### Pros

TODO

#### Cons

TODO
