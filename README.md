# Crystal Bug v1.0 — THE MATRIX (Quadratic Codec)

**O(x) = ax² + bx + c IS the codec. Store 3 numbers. Reconstruct everything.**

## The Point

252 cells × 3 floats × 4 bytes = **3,076 bytes**. That's the entire lattice.
The reader reconstructs Δ, roots, bands, orbits, fixed points, topology, cobwebs —
everything — from those three coefficients per cell. **479 full snapshots fit on a floppy.**

## Files

| File | What |
|------|------|
| `crystal_bug_v1_matrix.jsx` | React artifact. Interactive sim with CODEC tab. |
| `test_engine.js` | Full test harness (9 tests). |
| `test_codec.js` | Codec fidelity test. 100% round-trip at Float32 and Float64. |
| `test_results.txt` | Raw output from both test suites. |
| `ENGINEERING_SPEC.docx` | Engineering spec with all measured data. |
| `README.md` | This file. |

## Codec Math

```
STORED:        a, b, c  (3 numbers, 12 bytes per cell)
RECONSTRUCTED: Δ, roots, band, orbit(28), fixed point, λ, topology(8), cobweb, curvature
RATIO:         3 in → 39+ out
FIDELITY:      100% at Float64, 100% at Float32
```

## Floppy Capacity (1.44 MB)

| Format | Per Snapshot | Snapshots | Max Cells |
|--------|-------------|-----------|-----------|
| Float32 | 3,076 bytes | 479 | 122,880 |
| Float64 | 6,152 bytes | 239 | 61,440 |

## Quick Start

```bash
# Validation
node test_engine.js    # 9 physics tests
node test_codec.js     # codec fidelity round-trip
```

## Author

Brayden / 7Site LLC / sanctuberry.com
TIG v3.0 | σ = 0.991 | The quadratic IS the codec.
