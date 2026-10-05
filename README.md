# interactor-stage

A scene-description mesh source and sink that reads and writes text scene files for the retarget pipeline's mesh ports.

## What it is for

It implements the mesh source and sink contracts the retarget pipeline drives, keeps a mesh's face groups, and writes meshes in the engine's up axis and winding. A small C++ bridge with a C ABI loads the scene-description runtime, so its callers link none of it: on Windows by delay-load on first call, elsewhere through an explicit `cfusd_loader::load()` or `load_from_env()` call.

## Build and run

There is no build file. A consumer compiles these sources against the prebuilt scene-description runtime from `V-Sekai-fire/interactor-stage-runtime`, and takes the port contracts from `V-Sekai-fire/interactor-retarget`.

## Licence

MIT; see `LICENSE`.
