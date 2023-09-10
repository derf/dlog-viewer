# dlog-viewer – Viewer and Exporter for Keysight dlog Files

[**dlog-viewer**](https://finalrewind.org/projects/dlog-viewer/) loads voltage, current, and/or power measurements from .dlog files
produced by devices such as the Keysight N6705B DC Power Analyzer.  It is
specifically meant for .dlog files that were written to a USB stick by the
power analyzer itself, so no Keysight software is required for analyzing them.

![](https://finalrewind.org/projects/dlog-viewer/media/preview.png)

Measurements can be exported to CSV or plotted on-screen via matplotlib.  There
is also support for changepoint detection to automatically identify changes in
the observed device behaviour. This is meant to work around a lack of digital
synchronization signals in the logged power traces.

This program is not affiliated with Keysight and has not been thoroughly tested, as I only have a singly type of power analyzer at hand.
Use at your own risk.

## Usage

Obtain a .dlog file e.g. by using the instrument's data logger feature.
dlog-viewer options include:

* plots showing voltage, current, or power over time (`--plot`),
* simple statistics (`--stat`, `--skip`, `--limit`)
* changepoint detectiong using the PELT algorithm (`--pelt`),
* CSV export of raw measurements (`--csv-export`), and
* JSON export of measurements and detected changepoints (`--json-export`).

See `bin/dlog-viewer --help` for details.

## Dependencies

* Python 3, numpy, matplotlib, xml.etree
* Changepoint detection: python3-ruptures
