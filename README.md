# Meridian: Wild Frontier

**Meridian: Wild Frontier** is my Godot and C# project for a third-person, open-world action RPG. The project is intended to grow around modular gameplay systems and data-driven content, with a test-world concept that includes a landmark beacon.

## Project overview

The intended architecture emphasizes:

- **Data-driven content:** Use Godot resources for definitions such as items, weapons, quests, regions, and weather profiles.
- **Composable systems:** Keep gameplay responsibilities separated into focused components and services.
- **Decoupled communication:** Use signals for node relationships and a typed event bus for communication between unrelated systems.
- **Save and restore:** Build toward reliable serialization and save-state restoration.
- **Performance awareness:** Treat frame time and runtime telemetry as development concerns.

These points describe the project's design direction; they should not be read as confirmation that every planned feature is complete or performance-tested.

## Technology

- **Engine configuration:** Godot 4.6 feature declaration in `project.godot`
- **C# SDK:** Godot .NET SDK 4.7.2, as specified by `Meridian.csproj`
- **Runtime:** .NET 8
- **Language:** C#

The repository also includes project configuration, solution/build files, an icon, and Godot runtime/editor logs.

## Repository status

The current GitHub file tree contains the project and build configuration files plus logs, but does **not** currently contain the scene, source-code, asset, or test directories referenced by the project configuration and earlier architecture notes. In particular, `project.godot` points to `res://scenes/game/Game.tscn` and C# autoload scripts under `src/Meridian/`, which are not present in the current tracked file tree.

Because of that gap, a fresh clone of the current repository may not be runnable or buildable yet. The source files, scenes, assets, and tests need to be committed before the setup steps below can be verified end to end.

## Getting started

### Requirements

- Godot .NET with C# support
- .NET 8 SDK

### Clone this repository

```bash
git clone https://github.com/themagicians208-glitch/open_world_rpg.git
cd open_world_rpg
```

Once the missing project files are included, open `project.godot` in Godot .NET. You can then restore and build the C# project with:

```bash
dotnet restore
dotnet build
```

Run tests with `dotnet test` only after the test project and its dependencies have been added to the repository.

## Logs

- `godot-check.log` — Godot editor/import and class-registration output.
- `runtime-check.log` and `runtime10.log` — runtime-check output.

The logs are diagnostic artifacts, not a substitute for the project source. Review them alongside the corresponding source and scene files when troubleshooting.

## Roadmap

The intended direction includes player movement and camera systems, items and weapons, world/region streaming, vehicles, time and weather, quests and dialogue, NPC behavior, progression, and content polish. Treat these as roadmap areas until the corresponding implementation is present in the repository and verified.

## Credits and licensing

This repository does not currently include a `LICENSE` file. The project references Godot and the .NET ecosystem; add appropriate credits and confirm the license terms for any third-party libraries, add-ons, or assets before redistribution. Add a license only after deciding the reuse terms for the material you have the right to license.
