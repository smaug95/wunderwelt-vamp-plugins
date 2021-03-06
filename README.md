# Wunderwelt Vamp Plugins

This repository contains vamp plugins developed during the course "Wunderbare Welt der musikalischen Akustik: Analyse" at the University of Vienna 2016-2017.

## Contained Plugins

### Amplitude Follower:
A very very simple plugin which returns the maximum value of each block.

### Doppler Speed Calculator:
Returns the speed of a noise-emitting source in km/h by calculating it directly from the frequency difference
between the beginning and end of the event with the following formula:

```
(arrivingFreq - leavingFreq) / (arrivingFreq + leavingFreq) * 343 m/s * 3.6 => speed in km/h
```

Everything except for the FFT was implemented myself, also the peak finding. Because I had no time to implement a good smoothing
of the data, the plugin is very fragile when it comes to select the right parameter values.


## Installation
Under releases, download the latest release binaries for your platform (Windows not yet supported).
You need to copy the shared library file (.so, .dylib) and optionally the category file (.cat)
to your Vamp path, i.e. one of the following directories:

Mac:
* /Library/Audio/Plug-Ins/Vamp
* ~/Library/Audio/Plug-Ins/Vamp

Linux:
* ~/vamp
* ~/.vamp
* /usr/local/lib/vamp
* /usr/lib/vamp

## TODOS
* Use a smoothing algorithm (like Savitzky-Golay) before searching peaks. This should render the plugin much more reliable.
* Compile it for Windows
* Use strategy pattern for Peak Finding algorithms
