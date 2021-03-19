## Riroriro

- [Documentation](https://wvanzeist.github.io)
- [Github](https://github.com/wvanzeist/riroriro)

Riroriro is a Python package to simulate the gravitational waveforms of binary mergers of black holes and/or neutron stars, and calculate several properties of these mergers and waveforms, specifically relating to their observability by gravitational wave detectors.

## Features

- Simulating the gravitational waveform signal from a binary merger of two black holes, two neutron stars or a black hole and a neutron star and outputting the data of this signal in terms of frequency and strain amplitude.
- Using a gravitational wave output and given a detector noise spectrum (such spectra are made publicly available by LIGO), calculating the signal-to-noise ratio (SNR) of the signal at a given distance assuming optimal alignment.
- Calculating the horizon distance (maximum distance at which an event could be observed) for a gravitational wave model and a given detector.
- Given the optimal-alignment SNR of an event, evaluating its detectability, the probability that the event would be detected with a SNR above the commonly used threshold of 8, if the alignment would be arbitrary. These results could then be combined with population synthesis calculations to estimate how many of the predicted mergers would be detected.