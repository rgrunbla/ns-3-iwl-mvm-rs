# ns-3-iwl-mvm-rs

This repository contains the code associated with the paper "Simulation and Performance Evaluation of the Intel Rate Adaptation Algorithm". You can find the paper at [this address](https://remy.grunblatt.org/pdfs/Simulation_and_Performance_Evaluation_of_the_Intel_Rate_Adaptation_Algorithm.pdf).

This code implements the Intel Rate Adaptation Algorithm (Iwl-Mvm-Rs), a rate adaptation algorithm used in pretty much all modern Intel hardware, for the [NS-3 simulator](https://www.nsnam.org/).

As of today, this code is compatible with NS-3 version 3.30.

## Installation

Currently, the installation is a little bit manual, but can be summarized by the following steps:

- `cp ./intel-rate-wifi-manager.{h,cc} ns-allinone-3.30/ns-3.30/src/wifi/model/`;
- Edit `ns-allinone-3.30/ns-3.30/src/wifi/wscript` to add the intel-rate-wifi-manager;
- Recompile NS-3;

# Caveats

Currently, the code is pretty much specialized for intel-like hardware:

- Number of antennas has to be 2;
- Aggregation is always enabled, as we assume no realtime traffic (audio feeds) will be sent;

Before a potential merge in NS-3, the algorithm has therefore to be adapted to support more generic hardware (but reusing the same techniques).
