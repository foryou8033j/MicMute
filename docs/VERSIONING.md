# Versioning

MicMute uses the root `VERSION` file as the source of truth for application versioning.

## Regular version bump

1. Edit `VERSION`.
2. Build with `build.bat`.
3. Commit the version change.

The build script generates `obj/generated/AssemblyInfo.g.cs` and embeds the version into:

- `AssemblyVersion`
- `AssemblyFileVersion`
- `AssemblyInformationalVersion`

## Build a specific version locally

```powershell
.\build.ps1 -Version 1.2.3
```

or:

```bat
build.bat -Version 1.2.3
```

## GitHub Actions

The build workflow runs on pushes and pull requests to `master`. It uploads `bin/MicMute.exe` as a workflow artifact.

For tags named `v1.2.3`, the workflow uses `1.2.3` as the build version instead of the `VERSION` file.
