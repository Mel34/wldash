# wldash

A dashboard/launcher/control-panel thing for Wayland. Requires wlr-layer-shell-unstable-v1.

Consider this alpha-quality: While it works, *everything* is subject to change with a moments notice. You may end up pulling in the latest changes, and *poof*, wldash suddenly turns into an artisan espresso machine.

## How to use

1. Checkout: `git clone https://github.com/kennylevinsen/wldash`
2. Build: `cargo build --release`
3. Put somewhere: `cp target/release/wldash /usr/local/bin/wldash`
4. Run: `wldash`

To display wldash on all outputs, set `WLDASH_ALL_OUTPUTS=1`.

## How to use launcher

Assuming https://github.com/kennylevinsen/dot-desktop is installed: `eval "$(dot-desktop "$(dot-desktop | wldash)")"`

wldash simply takes a new-line separated list of strings, and returns the selection. dot-desktop generates this list, and afterwards processes the selection to return the proper instantiation string. Eval then executes it.

## Features

### Date and time

In nice, big letters!

### 3 month calendar

Scroll or click on the months to navigate.

### Battery level

Over upower, only visible if upower battery is detected

### Audio volume

Over pulseaudio, only visible if pulseaudio connection is successful. Scroll to adjust volume, right-click to toggle mute.

### Backlight control

Using backlight sys file, only visible of backlight is detected. Scroll to adjust, right-click to toggle between the extreme values.

### Launcher

Works like bemenu: pipe a list into wldash, and it will print out the selection made. Use https://github.com/kennylevinsen/dot-desktop if you want to launch using desktop files.

The launcher also accepts prefix operators to change its mode:
- `!`: Arbitrary command
- `=`: Calculator based on rcalc_lib. See https://docs.rs/rcalc_lib/0.9.3/rcalc_lib/

## Notable missing features:

- Scaling of any kind - all sizes are currently hardcoded in pixels
- Configurability
- Cleanup and reorganization
