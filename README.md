# weftfit/stage

Scene-description (**OpenUSD**) source+sink **adapter** for weftfit — implements
`retarget`'s `mesh_source` / `mesh_sink` ports by reading and writing `.usda`
stages. Named to avoid the OpenUSD trademark (kept only here in the description),
matching `stage_runtime`.

- **`adapters/bridge/`** — the `cloth_fit_usd` dlopen C-ABI bridge: the only unit
  that links `usd_ms`, so consumers link zero USD and USD's TBB stays isolated
  (dlsym stub on POSIX, delay-loaded import lib on llvm-mingw).
- **`adapters/io/`** — `USDReader` / `USDWriter`: mesh ⇄ `UsdGeomMesh`, preserving
  groups (native `UsdGeomSubset` + `polyfem:*` attrs); writes stage `upAxis="Y"` +
  mesh `orientation="rightHanded"` (canonical Godot frame).
- **`ports/`** — the contracts this adapter implements.

Depends on **[`stage_runtime`](https://github.com/v-sekai-multiplayer-fabric/fabric-stage-runtime)**
(prebuilt per-triplet `usd_ms`: `x86_64-linux-gnu`, `aarch64-apple-darwin`,
`x86_64-windows-msvc`, `x86_64-windows-gnu`).
