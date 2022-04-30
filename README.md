# Proton GE flatpak

Proton GE is a custom build of GloriousEggroll's custom distribution of Valve'scompatibility layer for running Windows games on Linux through Steam.

This repository contains recipies for building Proton from [source](https://github.com/GloriousEggroll/proton-ge-custom) on top of [freedesktop-sdk](https://gitlab.com/freedesktop-sdk/freedesktop-sdk) in flatpak format, intended for running from the [Steam flatpak](https://github.com/flathub/com.valvesoftware.Steam).

## Installation

This unofficial build isn't supported by GloriousEggroll nor Valve and wasn't tested with all possible games and cases. It can behave differently from upstream builds. Use at your own risk.

First [add](https://flatpak.org/setup) Flathub repository and install Steam from there, if not already. Then run
```
flatpak install com.valvesoftware.Steam.CompatibilityTool.Proton-GE
```

Recent vulkan extensions are required for Proton-GE to work properly. So install `mesa-git` by running
```
flatpak remote-add --user flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak install --user flathub-beta \
    org.freedesktop.Platform.GL.mesa-git//21.08 \
    org.freedesktop.Platform.GL32.mesa-git//21.08
```

And launch steam with
```
FLATPAK_GL_DRIVERS=mesa-git flatpak run com.valvesoftware.Steam
```

Or follow [the latest instructions from freedesktop](https://gitlab.com/freedesktop-sdk/freedesktop-sdk/-/wikis/Mesa-git).

## Running

Launch Steam flatpak and select "Proton GE (flatpak)" compatibility tool from drop-down list.
