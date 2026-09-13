# PenTraceTools

Source-first tools for understanding pen input and improving digital drawing.

| Repository | What it does |
| --- | --- |
| [pen-stabilizer](https://github.com/PenTraceTools/pen-stabilizer) | Small MIT C++17 header-only position-correction library |
| [pen-trace-lab](https://github.com/PenTraceTools/pen-trace-lab) | Windows pen/touch recording, replay, speed metrics and same-input filter comparisons |

**One algorithm source, two independently versioned projects.** PenTraceLab compiles
the shared library directly; drawing applications can integrate that same pinned
source. No required DLL, driver, service or runtime download.

The [InfiniPaint fork](https://github.com/alexiokay/infinipaint-Custom/tree/graphite-ui)
is an external consumer. The [upstream integration proposal](https://github.com/ErrorAtLine0/infinipaint/pull/98)
is a draft, not an endorsement or merged upstream feature. InfiniPaint remains the
work of its original creator, [ErrorAtLine0](https://github.com/ErrorAtLine0/infinipaint).

## Start here

- Integrate: [library API and example](https://github.com/PenTraceTools/pen-stabilizer#native-integration).
- Measure: [PenTraceLab instructions](https://github.com/PenTraceTools/pen-trace-lab).
- Update safely: [source versioning workflow](https://github.com/PenTraceTools/.github/blob/main/VERSIONING.md).
- Compare InfiniPaint pressure/rendering stages: [replay utility](https://github.com/alexiokay/infinipaint-Custom/blob/graphite-ui/docs/BRUSH_PIPELINE.md).
- View real-device examples: [Test 6 comparison gallery and SVGs](https://github.com/PenTraceTools/pen-trace-lab/tree/main/docs/comparisons/test6), including settings, limitations and the future chart protocol.

Current shared position core: **v0.1.0 / algorithm revision 1**, pinned by consumers.
App versions/releases are separate. Check the selected app branch's dependency pin
and build instructions; a documentation update is not an executable release.

## Honest limits

Windows reports are not physical ground truth. Bounded correction can reduce some
wobble, but cannot guarantee perfect intended paths, zero delay or device-independent
results. Bigger neighborhoods can soften detail. Synthetic regression tests establish
software properties; real-device drawing and renderer performance still need testing.

Algorithm issues belong in pen-stabilizer; capture/diagnostic issues in PenTraceLab;
host pressure/curve/rendering issues in the drawing app. Share recordings only when
you choose to make their contents public.
