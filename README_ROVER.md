# Siberia's Last Hope Rover — PX4 fork

Fork of PX4 v1.17.0 (branch `rover`) for a 4-wheel skid-steer rover on a
Pixracer (`px4_fmu-v4`) with a Raspberry Pi 5 companion (ROS 2 Jazzy over
uXRCE-DDS on TELEM2). Navigation is indoor, from external visual odometry.

## What is different from upstream

- `boards/px4/fmu-v4/rover.px4board` — slim fmu-v4 target: only the
  differential rover module, no aircraft modules, no unused drivers.
- `ROMFS/px4fmu_common/init.d/airframes/50100_slh_rover` — airframe
  (SYS_AUTOSTART 50100): base parameters only, no controller tuning.
- `.github/workflows/rover-build.yml` — the only CI workflow
  (firmware build + SITL build); upstream workflows were removed.

## Build

    make px4_fmu-v4_rover      # -> build/px4_fmu-v4_rover/px4_fmu-v4_rover.px4

## Before first drive (TODO placeholders in the airframe)

- `RC_MAP_KILL_SW` — set to the real transmitter channel.
- `RD_WHEEL_TRACK` — measure the distance between left and right wheels.
- `RO_MAX_THR_SPEED` — measure speed at full throttle.
- Tune the rover controllers; none are tuned in the airframe.
