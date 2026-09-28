# Harborwatch 1A MVP

An offline-friendly, single-page prototype for the hackathon problem **1A: Naval / Army Geospatial & Multimodal Threat Detection**.

## Run it

Open `index.html` in a modern browser. No build step, account, API key, install, or server is required. The interface is designed for laptop presentation and adapts to smaller screens.

## Demo flow (about 2 minutes)

1. Introduce the coastal watch map as an illustrative, simulated operating picture.
2. Point out the three evidence layers: monitored tracks, alert markers, and the sensor reports in the legend. Toggle **COVERAGE** to show the sample coverage rings.
3. Select **Track identity mismatch**. Explain that the example flags a 3.8 km disagreement between two simulated sources, shows source age and confidence, and suggests checking timestamps and association.
4. Open **Unusual route deviation** and explain that a rule-based cue is a prompt for review, not a threat determination.
5. Use **Mark reviewed** or **Dismiss** to demonstrate human control and the live queue count. The **HIGH / REVIEW** filters narrow the queue.
6. Close by describing how open AIS, satellite, or benchmark imagery feeds could replace the synthetic inputs in a later iteration, with evaluation against labeled data.

## What is implemented

- Responsive geospatial-style coastal map with track lines, vessel markers, alert halos, sensor symbols, and optional coverage rings.
- Three seeded alert examples with evidence, source age, illustrative confidence, coordinates, and analyst guidance.
- Alert filtering, selection from either the queue or map, review/dismiss actions, and live queue counters.
- Explicit simulation and data-status labels throughout the interface.

## Scope and limitations

This is a hackathon interface prototype. The map geometry and all positions, tracks, measurements, alerts, and confidence values are illustrative and synthetic. Alert examples are hard-coded demonstrations, not model outputs. It does not connect to live AIS, satellite, radar, drone, GIS, or classified feeds; it has no trained detection model, backend, authentication, persistence, or deployment hardening. It should not be used for navigation or operational decisions.

The map uses inline SVG and CSS, so core functionality works without network access. Google Fonts are loaded from a CDN when available; the browser falls back to local system fonts otherwise.

## Next build steps

1. Replace the hard-coded scenario with an openly licensed sample dataset, preserving source, timestamp, and license metadata.
2. Add a small local API and an explainable anomaly scorer, then evaluate alerts against labeled examples and report precision/recall and false-alert counts.
3. Add exportable analyst review history and a repeatable demo reset flow.
