# vlc-srt-urlparam-mod
A modified srt.c access module for adding `streamid` parameter support to VLC. Please excuse the bad code, it was made in a very short amount of time (but works well)

## Notice
This is uncompiled source code! Meaning you will have to compile VLC yourself in order to be able to use this modification.

## Using this yourself (Ubuntu)
This is not a step-by-step guide, only the basic information required to get it working. I built and use this on Linux, your results may vary.

- Download VLC v3.0.11 source code from the VLC website: https://www.videolan.org/vlc/download-sources.html
- You must remove any existing version of vlc and libvlc via apt and/or snap.
- Uncomment the `deb-src` line for `universe` in your `/etc/apt/sources.list`, then run `sudo apt update`
- Install all necessary VLC dependencies with `sudo apt build-dep vlc`
- Extract VLC with `tar -xvf vlc-3.0.11.tar.xz`
- Replace `vlc-3.0.11/modules/access/srt.c` with the file contained in this repository.
- CD into the VLC directory and run `./configure`, then assuming it works run `./compile`. Compiling will take a long time.
- To install it onto your system, run `sudo make install`, and then `sudo ldconfig`.

And you should be done! Here's an example SRT URL containing a `streamid` parameter: `srt://123.123.123.123:6969?streamid=app/streamname`
