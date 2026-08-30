# Topotoy Godot patches

This branch is based on the upstream `4.7.1-stable` tag and carries the
smallest engine changes needed by Topotoy's ReSTIRKit integration.

## Patches

1. **Release-build BLAS validation**
   Runs the index-buffer `max_index` check only in debug builds, where Godot
   records that value. Release builds intentionally store `UINT32_MAX`, so the
   same check would reject every indexed bottom-level acceleration structure.

Topotoy's effective engine changes are consolidated into one commit above the
official source revision so the maintained delta is easy to audit and rebase.

## Distribution

Tags named `4.7.1-topotoy.N` identify reproducible source snapshots. Matching
Windows editor and export-template bundles plus their SHA-256 checksums are
attached to the corresponding GitHub release. CoreKit's shared Godot
toolchain builder and verifier produce and qualify those artifacts; generated
binaries are not committed to Git.

The unmodified Godot project remains the upstream source:
<https://github.com/godotengine/godot>.
