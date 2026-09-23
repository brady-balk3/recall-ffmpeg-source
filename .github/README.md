# FFmpeg source for Recall

[Recall](https://github.com/brady-balk3/recall-public) is a free, open-source Windows app that turns long streams and gaming VODs into short vertical clips ready to post. You give it a Twitch VOD or a local recording and it finds the moments worth clipping: big reactions, funny exchanges, clutch plays. It frames your facecam and gameplay for vertical video and captions the clip. You review and adjust each one before export. Everything runs on your own PC, and your recordings never leave it.

Recall uses FFmpeg to decode your recordings and render the finished clips. This repository holds the **complete source code for the exact `ffmpeg.exe` bundled with Recall**, as FFmpeg's license requires. You only need it if you want to inspect or rebuild that FFmpeg. To use Recall, go to the [Recall repository](https://github.com/brady-balk3/recall-public).

## What's here

- **This repository's files** are FFmpeg's own source at revision [`9d4ca21220`](https://github.com/FFmpeg/FFmpeg/commit/9d4ca21220bfd3f06fc8bfc90ddf0f6d0a484611), unmodified. See `RECALL_UPSTREAM.txt`.
- **[The release](../../releases/latest)** has the rest as downloads:
  - the source archive of every library built into that FFmpeg (listed below),
  - the build recipe: [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) at `a1b5c414d3c5`, the scripts that produced the binary,
  - `BUILD_IDENTITY.txt`: the `ffmpeg -version` output of the shipped binary, including its full configure line,
  - `SHA256SUMS.txt`: checksums for every file.

## The build

| | |
| --- | --- |
| Version | `n9.0.1-6-g9d4ca21220-20260824` |
| Packager | BtbN/FFmpeg-Builds, `win64-lgpl` variant |
| License | LGPL-3.0-or-later (`--enable-version3`, no `--enable-gpl`) |
| Linking | static; Recall runs `ffmpeg.exe` as a separate program |

To rebuild, check out the build recipe at the revision above. Its scripts pin each library to the same revisions as the archives in the release.

## Library sources

Each library is pinned to the exact revision the build recipe uses.

| Library | Upstream | Revision | Release file |
| --- | --- | --- | --- |
| libiconv | [git.savannah.gnu.org/git/libiconv](https://git.savannah.gnu.org/git/libiconv) | `5e517e5bf0e1` | `libiconv-5e517e5bf0e1b4575ad431e81d7a4750fa2b284e.tar.gz` |
| gnulib (for libiconv) | [git.savannah.gnu.org/git/gnulib](https://git.savannah.gnu.org/git/gnulib) | `09b1597470c4` | `gnulib-09b1597470c456aeac7e7d19b214821d4526934d.tar.gz` |
| zlib | [github.com/madler/zlib](https://github.com/madler/zlib) | `e3dc0a85b703` | `madler-zlib-e3dc0a85b7032e98380dec011bc8f2c2ee0d8fca.tar.gz` |
| fribidi | [github.com/fribidi/fribidi](https://github.com/fribidi/fribidi) | `04a8cb7a3674` | `fribidi-fribidi-04a8cb7a3674717e509c79cd6ee3e127d0c75f4c.tar.gz` |
| gmp | [github.com/BtbN/gmplib](https://github.com/BtbN/gmplib) | `9994908f090c` | `BtbN-gmplib-9994908f090c694f8a152d660dc6852e0c48557a.tar.gz` |
| libxml2 | [github.com/GNOME/libxml2](https://github.com/GNOME/libxml2) | `c63248941708` | `GNOME-libxml2-c63248941708bc1d2e3a4292954593312212f6ca.tar.gz` |
| xz | [github.com/tukaani-project/xz](https://github.com/tukaani-project/xz) | `c8b8ab2ef1eb` | `tukaani-project-xz-c8b8ab2ef1eb0a0217ad2027d7f5d242ceb944d3.tar.gz` |
| harfbuzz | [github.com/harfbuzz/harfbuzz](https://github.com/harfbuzz/harfbuzz) | `d8dabe259459` | `harfbuzz-harfbuzz-d8dabe2594596c656b54c3b0072f3aa3093f30a9.tar.gz` |
| libvorbis | [github.com/xiph/vorbis](https://github.com/xiph/vorbis) | `1b75110b5a27` | `xiph-vorbis-1b75110b5a2754ba1931d82dd83cb822b266a21d.tar.gz` |
| opencl | [github.com/KhronosGroup/OpenCL-Headers](https://github.com/KhronosGroup/OpenCL-Headers) | `c9c8ccfab584` | `KhronosGroup-OpenCL-Headers-c9c8ccfab584f9f7610057c4633dbd3df7e012cc.tar.gz` |
| vmaf | [github.com/Netflix/vmaf](https://github.com/Netflix/vmaf) | `e80d6c593e6e` | `Netflix-vmaf-e80d6c593e6e2327687dccd00b7cc9c91036d79f.tar.gz` |
| vulkan-loader | [github.com/BtbN/Vulkan-Shim-Loader](https://github.com/BtbN/Vulkan-Shim-Loader) | `65b3936528cd` | `BtbN-Vulkan-Shim-Loader-65b3936528cd92eb4ea3de485d03f858a3850484.tar.gz` |
| libaribb24 | [github.com/nkoriyama/aribb24](https://github.com/nkoriyama/aribb24) | `5e9be272f96e` | `nkoriyama-aribb24-5e9be272f96e00f15a2f3c5f8ba7e124862aec38.tar.gz` |
| chromaprint | [github.com/acoustid/chromaprint](https://github.com/acoustid/chromaprint) | `aed8eba2202d` | `acoustid-chromaprint-aed8eba2202dd9d7b3b0a56c77904cc805490d72.tar.gz` |
| ffnvcodec | [github.com/FFmpeg/nv-codec-headers](https://github.com/FFmpeg/nv-codec-headers) | `eddcea9e27f6` | `FFmpeg-nv-codec-headers-eddcea9e27f6b772057c9b3f87de2cc1737faffc.tar.gz` |
| gme | [github.com/libgme/game-music-emu](https://github.com/libgme/game-music-emu) | `fe8da4b6d387` | `libgme-game-music-emu-fe8da4b6d3876d7542c2fb69d94487e19836d678.tar.gz` |
| kvazaar | [github.com/ultravideo/kvazaar](https://github.com/ultravideo/kvazaar) | `d6815293f34a` | `ultravideo-kvazaar-d6815293f34a094e26ba6c50b8644660ddc13e09.tar.gz` |
| lcevcdec | [github.com/v-novaltd/LCEVCdec](https://github.com/v-novaltd/LCEVCdec) | `a254bd474649` | `v-novaltd-LCEVCdec-a254bd474649e5dcd8182689ac414420bfe8d8c3.tar.gz` |
| libaribcaption | [github.com/xqq/libaribcaption](https://github.com/xqq/libaribcaption) | `c64c23b8905b` | `xqq-libaribcaption-c64c23b8905ba514b87c9789269e9f66f949ffe0.tar.gz` |
| libass | [github.com/libass/libass](https://github.com/libass/libass) | `3087d2b2ffda` | `libass-libass-3087d2b2ffda76602a17f9b09d25cb8addc8d313.tar.gz` |
| libbluray | [code.videolan.org/videolan/libbluray](https://code.videolan.org/videolan/libbluray) | `065247e5ef40` | `libbluray-065247e5ef40ccf39857db81e2c1368354a23ef8-with-submodules.tar.gz` |
| libjxl | [github.com/libjxl/libjxl](https://github.com/libjxl/libjxl) | `d089091afeb7` | `libjxl-libjxl-d089091afeb7b00b3d0fec6f019d35eaa3b2b410.tar.gz` |
| libmp3lame | [svn.code.sf.net/p/lame/svn/trunk/lame](https://svn.code.sf.net/p/lame/svn/trunk/lame) | `r6761` | `lame-svn-r6761.tar.gz` |
| libopus | [github.com/xiph/opus](https://github.com/xiph/opus) | `3da9f7a6db1c` | `xiph-opus-3da9f7a6db1c05c3996cb363a9d1931a978bf1be.tar.gz` |
| libplacebo | [code.videolan.org/videolan/libplacebo](https://code.videolan.org/videolan/libplacebo) | `22ee762e8e08` | `libplacebo-22ee762e8e0890fc54068beb670310f0edce7263-with-submodules.tar.gz` |
| libssh | [gitlab.com/libssh/libssh-mirror](https://gitlab.com/libssh/libssh-mirror) | `1dc52926c54b` | `libssh-1dc52926c54b59ea7a3350a59a476bb76da3ff33.tar.gz` |
| libtheora | [github.com/xiph/theora](https://github.com/xiph/theora) | `28fd5ec77f0a` | `xiph-theora-28fd5ec77f0ad0e07a371cef1047828116f6bd8a.tar.gz` |
| libzmq | [github.com/zeromq/libzmq](https://github.com/zeromq/libzmq) | `46493370217a` | `zeromq-libzmq-46493370217ac135246617fa2f6ac819d8b61bfc.tar.gz` |
| lilv | [github.com/lv2/lilv](https://github.com/lv2/lilv) | `4b8f30055fa5` | `lv2-lilv-4b8f30055fa5cb4134a2eb45fc1555bc04289314.tar.gz` |
| onevpl | [github.com/intel/libvpl](https://github.com/intel/libvpl) | `674d015bcb29` | `intel-libvpl-674d015bcb294bc39fa276e99a652ea045423e82.tar.gz` |
| openal | [github.com/kcat/openal-soft](https://github.com/kcat/openal-soft) | `c157b87cb9eb` | `kcat-openal-soft-c157b87cb9eb58d747748e49f82ee4a64d1dcf8b.tar.gz` |
| openapv | [github.com/AcademySoftwareFoundation/openapv](https://github.com/AcademySoftwareFoundation/openapv) | `d625af974550` | `AcademySoftwareFoundation-openapv-d625af974550427e638574db61c270fe7f8c5a73.tar.gz` |
| openh264 | [github.com/cisco/openh264](https://github.com/cisco/openh264) | `98bc7cbbeb73` | `cisco-openh264-98bc7cbbeb7381c94ef8f9a5d158327abbf6b8b9.tar.gz` |
| openjpeg | [github.com/uclouvain/openjpeg](https://github.com/uclouvain/openjpeg) | `402ef5862195` | `uclouvain-openjpeg-402ef5862195b177ea0a7788f2a6ef2804e62285.tar.gz` |
| openmpt | [github.com/OpenMPT/openmpt](https://github.com/OpenMPT/openmpt) | `1b000d4bca07` | `OpenMPT-openmpt-1b000d4bca071364157b5d35940efe4feecd2e0a.tar.gz` |
| rav1e | [github.com/xiph/rav1e](https://github.com/xiph/rav1e) | `564ae3b0007a` | `xiph-rav1e-564ae3b0007ae2b06893fd7166bf88c5a84c5b63.tar.gz` |
| sdl | [github.com/libsdl-org/SDL](https://github.com/libsdl-org/SDL) | `a2e7c76bda17` | `libsdl-org-SDL-a2e7c76bda17c853ba93c7d2c9fdddf8a9d621d1.tar.gz` |
| snappy | [github.com/google/snappy](https://github.com/google/snappy) | `747488a9f3d0` | `google-snappy-747488a9f3d0daf9b639b6704d7188fba48af179.tar.gz` |
| soxr | [git.code.sf.net/p/soxr/code](https://git.code.sf.net/p/soxr/code) | `945b592b7047` | `soxr-945b592b70470e29f917f4de89b4281fbbd540c0.tar.gz` |
| srt | [github.com/Haivision/srt](https://github.com/Haivision/srt) | `fcae57145c00` | `Haivision-srt-fcae57145c000a9e7b72aa777adb8f85c2463242.tar.gz` |
| twolame | [github.com/njh/twolame](https://github.com/njh/twolame) | `6fced852d4d5` | `njh-twolame-6fced852d4d5cfad58cf9dbe3ea619b08e87d398.tar.gz` |
| uavs3d | [github.com/uavs3/uavs3d](https://github.com/uavs3/uavs3d) | `0e20d2c29185` | `uavs3-uavs3d-0e20d2c291853f196c68922a264bcd8471d75b68.tar.gz` |
| libva | [github.com/intel/libva](https://github.com/intel/libva) | `6b07f7100512` | `intel-libva-6b07f7100512817f736967e899b8c26313c20623.tar.gz` |
| vvenc | [github.com/fraunhoferhhi/vvenc](https://github.com/fraunhoferhhi/vvenc) | `0f2e874451d6` | `fraunhoferhhi-vvenc-0f2e874451d6b194615e5dfefdc96796a7da00f4.tar.gz` |
| zimg | [github.com/sekrit-twc/zimg](https://github.com/sekrit-twc/zimg) | `f6cc75ad23db` | `sekrit-twc-zimg-f6cc75ad23db1bb9c53673c15523e6b6e960ffc6.tar.gz` |
| zvbi | [github.com/zapping-vbi/zvbi](https://github.com/zapping-vbi/zvbi) | `d3a5ee9f2b04` | `zapping-vbi-zvbi-d3a5ee9f2b047bf16cd1ee5ccf6ec05ee75409d0.tar.gz` |

These components are also part of the build, but their licenses don't require distributing source, so they aren't bundled here:

| Component | License |
| --- | --- |
| mingw | mingw-w64 runtime/winpthreads: ZPL/MIT/public domain; libgcc under GCC runtime exception |
| fontconfig | MIT-style |
| freetype | FreeType License (FTL) option of FTL/GPLv2 dual license |
| aom | BSD-2-Clause + AOM patent license |
| dav1d | BSD-2-Clause |
| librist | BSD-2-Clause |
| libvpx | BSD-3-Clause |
| libwebp | BSD-3-Clause |
| opencore-amr | Apache-2.0 |
| svtav1 | BSD-3-Clause-Clear/AOM |
| schannel | Windows system component, not distributed |
| amf | AMD AMF headers, MIT |

## Licenses

FFmpeg and every library keep their own licenses, which are included in each source archive. See FFmpeg's `LICENSE.md` and the `COPYING.*` files in this repository.

This is a read-only source mirror. Bug reports about FFmpeg belong [upstream](https://ffmpeg.org/bugreports.html). Questions about Recall go to the [Recall repository](https://github.com/brady-balk3/recall-public).
