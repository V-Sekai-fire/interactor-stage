# interactor-stage

A scene-description mesh source and sink that reads and writes text scene files for the retarget pipeline's mesh ports.

## What it is for

It implements the mesh source and sink contracts the retarget pipeline drives, keeps a mesh's face groups, and writes meshes in the engine's up axis and winding. A small C bridge loads the scene-description runtime when it is first called, so its callers link none of it.

## Build and run

There is no build file. A consumer compiles these sources against the prebuilt scene-description runtime from the stage runtime repository.

## Licence

MIT; see `LICENSE`.
