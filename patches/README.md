# Dependency Patches

## react-image-crop@11.0.10

- Reason: With a fixed `aspect`, upstream hides N/E/S/W handles and their drag bars (only corners remain). We add `hideEdgeHandlesWhenAspectLocked` (still defaults to `true`) and set it off in the editor so mid-edge grips stay usable. Turning those handles back on exposed upstream resize math that still anchored N/S/E/W like a corner (e.g. north dragged from the bottom-right), so the patch adds edge-aware resizing that keeps the opposite **edge** centered (horizontal midpoint for N/S, vertical midpoint for E/W) while preserving aspect and bounds.
- Upstream: https://github.com/dominictobias/react-image-crop
- Remove when: upstream release includes equivalent behavior (then drop patch, unpin, bump).
