# Night City Street Series

Nine sequential, replayable street races for Cyberpunk 2077. The organiser's
phone introduction opens the first event; each first-place finish unlocks the
next. Winning all nine awards a one-time €$100,000 bonus, in addition to the
ordinary €$10,000 race payouts. Losses can be retried. Won races become replayable after the championship is complete.
Startup uses Ghostline Quest Core slot 1 and does not depend on H10 or CET.
All nine races use population-owned NPCs and vehicles. Their standing workspots
and spawn positions belong to the race package, so placement edits do not
require rebuilding the core's community-workspot registry.

| Round | Race | Distance | Player car | Opponent field |
| --- | --- | --- | --- | --- |
| 1 | Opening Run | 5.48 km | Own car | Five selected street-car crews |
| 2 | Dockside Dash | 3.52 km | Own car | Tuned compacts, Shion and Type-66 |
| 3 | MaiMai Mayhem | 1.22 km | Provided MaiMai E126 | Five MaiMai E126s |
| 4 | Heavy Metal | 5.04 km | Own car | Type-66 variants and Alvarado |
| 5 | Dust Trail | 6.36 km | Provided Quartz Sidewinder | Nomad cars |
| 6 | Coastline Run | 3.84 km | Own car | Shions and tuned Quartzes |
| 7 | Factory Shift | 2.58 km | Provided Type-66 640 TS | Type-66 variants and Alvarado |
| 8 | Executive Express | 7.16 km | Own car | Outlaws, Turbo-R, Type-66s and Shion |
| 9 | Night City Grand Prix | 15.34 km | Own car | Five selected performance-car crews |

Each field contains five crews with selected vanilla race-driver and passenger
records and explicit vehicle appearances. Every course uses one ordered pass,
including routes that return near their start. Starting positions are surveyed,
with the player at the back. Opponent speed targets use the
vanilla 100 m/s default; the cars' handling and performance still differ.
Checkpoints use the game's shipped MQ056 entity with per-placement direction
and finish selectors; no custom checkpoint entity files are required.

`projects/series/modio_championship.json` owns race order, invitations and the final reward. Each file in
`projects/` contains its complete route, starting marks, vehicles, crew and race
settings. These are source inputs for the installed Race Builder. See
[editing and building the championship](docs/authoring.md) for setup and packaging:

```sh
ghostline-race-builder validate-series projects/series/modio_championship.json --projects projects
ghostline-race-builder build-series projects/series/modio_championship.json --projects projects --out builds/championship --game "path/to/Cyberpunk 2077"
```

To edit these source files directly in the UI, serve the builder with
`--workspace projects` when running from this repository.

Courses follow the native drivable traffic network, including road elevations.
Before release, drive every course and check roadside activation, grid and
finish clearance, opponent behavior, provided-car cleanup, save/load, unlocks,
replays and the final reward. Native package verification does not establish
in-game behavior or console distribution compatibility.

For local cross-platform testing, extract the generated `modio/` ZIP into the
game's `r6/c77` directory. Keep the archive and JSON-formatted registration in
their package subfolder and the JSON tweaks under `r6/c77/tweaks`.
