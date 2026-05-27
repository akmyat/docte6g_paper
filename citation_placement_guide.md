# Citation Placement Guide for Your Paper

This guide shows where to insert `\cite{...}` in the **Introduction** and **Background** sections of your paper.

The goal is not to cite every sentence. Instead, cite the main technical claims: 6G motivation, channel modeling, simulator choice, Sionna RT, ns-3/5G-LENA, MIMO/ISAC, and energy evaluation.

---

# 1. Introduction Section

## 1.1 Environment-aware 6G motivation

### Put citation after this sentence

```latex
Sixth-generation cellular and next-generation wireless local-area networks are increasingly defined by their interaction with the radio environment rather than by abstract path-loss exponents \cite{tr38901,alsamman_mmwave,han_thz}.
```

### Put citation after this sentence

```latex
Joint communication and sensing, integrated access and backhaul, reconfigurable intelligent surfaces, and AI-driven beam management all require simulation tools that can resolve geometry, materials, and antenna directivity at the level of individual rays \cite{zhou_isac,gao_isac_mimo,cazzella_dt_mimo}.
```

### Reason

Use these citations because this paragraph motivates why abstract path-loss models are not enough for 6G, ISAC, and environment-aware wireless systems.

---

## 1.2 ns-3 and protocol-stack fidelity

### Put citation after this sentence

```latex
ns-3 is the de facto open-source platform for that protocol-stack fidelity \cite{ns3}.
```

### Put citation after this sentence

```latex
It ships with a modular contrib system, a stable C++ API for propagation and spectrum models, and an actively maintained 5G NR module, 5G-LENA \cite{ns3,5glena}.
```

### Put citation after this sentence

```latex
Its propagation models, however, are by design mathematically tractable rather than environment-specific: Friis, log-distance, 3GPP TR 38.901 spatial-channel models, and a handful of empirical alternatives \cite{tr38901,5glena}.
```

### Reason

Use these citations because this paragraph introduces ns-3, 5G-LENA, and the limitation of built-in propagation models.

---

## 1.3 Sionna RT motivation

### Put citation after this sentence

```latex
NVIDIA's Sionna RT is, conversely, a differentiable ray tracer with support for planar antenna arrays, polarization, and scene-based radio propagation \cite{sionna,sionnart}.
```

### Put citation after this sentence

```latex
It is, however, a Python library oriented around standalone physical-layer and link-level studies; it does not implement MAC, RLC, PDCP, or full network protocol behavior \cite{sionna,sionnart,5glena}.
```

### Reason

Use these citations to justify why Sionna RT and ns-3 are complementary.

---

## 1.4 Prior socket-coupled integration

### Put citation after this sentence

```latex
Bridging the two has historically meant socket-coupling: launching the ray tracer as a separate process and exchanging position and channel data over ZMQ or TCP \cite{ns3sionna}.
```

### Put citation after this sentence

```latex
The reference implementation ns3sionna follows this pattern, and our own measurements confirm that under mobility-dominated load it imposes prohibitive overhead \cite{ns3sionna}.
```

### Reason

Use this citation because your runtime comparison directly compares against ns3sionna.

---

## 1.5 Contribution list

### Contribution 1: embedded integration

```latex
An embedded integration, contrib/sionnart, in which the Python interpreter and Sionna RT live inside the ns-3 process via pybind11 \cite{sionna,sionnart,pybind11}.
```

### Contribution 3: 5G NR evaluation

```latex
Campaign II examines the impact of channel realism on 5G NR networks across free space, urban macro, and urban micro environments \cite{5glena,tr38901,bojovic_mimo}.
```

### Energy-aware evaluation claim

```latex
The evaluation also studies how propagation realism changes throughput, link adaptation, and gNB/UE energy estimates \cite{5glena,samorzewski_energy}.
```

---

# 2. Background Section

# 2.1 Massive MIMO for 6G

## Put citation after this sentence

```latex
Multiple-Input Multiple-Output (MIMO) technology is a fundamental building block of 6G systems \cite{bojovic_mimo,cazzella_dt_mimo}.
```

## Put citation after this sentence

```latex
Large-scale MIMO antenna arrays are essential for operating in high-frequency bands such as mmWave and THz \cite{uwaechia_mmwave,han_thz}.
```

## Put citation after this sentence

```latex
With the evolution of MIMO antenna arrays, they provide highly directional beamforming and increased angular resolution, allowing the network to distinguish users and objects in the environment \cite{bojovic_beamforming,gao_isac_mimo}.
```

## Put citation after this sentence

```latex
In particular, MIMO plays an important role in Integrated Sensing and Communication (ISAC), where the wireless channel is exploited not only for data transmission but also for environment sensing \cite{zhou_isac,gao_isac_mimo,hua_isac_beamforming}.
```

## Put citation after this sentence

```latex
However, conventional stochastic channel models, which are widely used in simulators, are designed for statistical performance evaluation and lack the geometric information required for applications such as ISAC \cite{tr38901,alsamman_mmwave,han_thz}.
```

---

# 2.2 Stochastic vs Deterministic Channel Modeling

## Put citation after this sentence

```latex
Stochastic models rely on statistical distributions to represent large-scale effects such as path loss and shadowing as well as small-scale fading through multipath clusters \cite{tr38901}.
```

## Put citation after this sentence

```latex
These models are computationally efficient and widely adopted in system-level simulators to evaluate average network performance across standardized deployment scenarios \cite{tr38901,5glena}.
```

## Put citation after this sentence

```latex
Even though they are suitable for large-scale evaluation, they lack site-specific realistic geometric information about the environment \cite{alsamman_mmwave,han_thz}.
```

## Put citation after this sentence

```latex
While full-wave solutions based on Maxwell's equations are computationally infeasible at network scale, high-frequency approximations such as ray tracing provide a practical alternative \cite{alsamman_mmwave,han_thz}.
```

## Put citation after this sentence

```latex
This is especially important for 6G research because mmWave and THz frequency bands are highly directional and sensitive to environment geometry \cite{uwaechia_mmwave,han_thz}.
```

---

# 2.3 Ray-Tracing Based Simulation

## Put citation after this sentence

```latex
Ray tracing is a deterministic channel modeling technique that provides a physically grounded representation of radio signal propagation \cite{alsamman_mmwave,han_thz}.
```

## Put citation after this sentence

```latex
It models how electromagnetic waves interact with the environment by considering reflection, diffraction, and scattering \cite{alsamman_mmwave,raymobtime_sionna}.
```

## Put citation after this sentence

```latex
Ray tracing has been widely used since the 1990s for modeling radio propagation in complex environments \cite{alsamman_mmwave}.
```

## Put citation after this sentence

```latex
Its deterministic nature enables accurate prediction of signal strength, delay spread, and angle of arrival, which are crucial for advanced wireless communication systems \cite{han_thz,raymobtime_sionna}.
```

## Put citation after this sentence

```latex
Recent advances in computing hardware, especially GPUs and parallel processing, have made ray tracing more practical for large-scale simulations \cite{sionnart,raymobtime_sionna,cazzella_dt_mimo}.
```

---

# 2.4 Simu5G and Sionna Prior Integration Limitations

## Put citation after this sentence

```latex
Simu5G is an open-source 5G system-level simulator built on the OMNeT++ framework \cite{omnet,simu5g}.
```

## Put citation after this sentence

```latex
Simu5G uses Network Description Language (NED) for topology description and C++ for the behavior of the network and applications \cite{omnet,simu5g}.
```

## Put citation after this sentence

```latex
In addition, it uses statistical models for channel modeling, which are not as accurate as ray-traced models for representing the physical environment \cite{simu5g,alsamman_mmwave,han_thz}.
```

## Put citation after this sentence

```latex
Despite our previous efforts to integrate Sionna RT with Simu5G for MIMO antenna systems with ray-tracing capabilities, we encountered several limitations that motivated our transition to ns-3 for our 6G simulations \cite{simu5g,sionna,sionnart,ns3,5glena}.
```

---

# 2.5 ns-3

## Put citation after this sentence

```latex
ns-3 is an open-source, discrete-event network simulator developed in C++ with support for integration with Python \cite{ns3}.
```

## Put citation after this sentence

```latex
The broad community has continuously contributed to the network simulator, which now supports different channel models such as Ethernet, Wi-Fi, LTE, and WiMAX \cite{ns3}.
```

## Put citation after this sentence

```latex
Each time a node sends a packet, the channel calls a statistical or stochastic model, such as Friis, log-distance, or the 3GPP propagation model, to calculate path loss and transmission delay \cite{ns3,tr38901}.
```

---

# 2.6 5G-LENA NR Module

## Put citation after this sentence

```latex
5G-LENA NR is an extension of ns-3 developed by CTTC for simulating 3GPP-compliant 5G NR cellular networks across both sub-6 GHz and mmWave frequency ranges \cite{5glena}.
```

## Put citation after this sentence

```latex
The MAC layer in 5G-LENA supports flexible schedulers for both TDMA and OFDMA-based access, while the PHY layer handles advanced MIMO models and MCS adaptation \cite{5glena,bojovic_mimo,bojovic_beamforming}.
```

## Put citation after this sentence

```latex
While 5G-LENA NR provides the protocol stack for 5G NR, it still relies on standard ns-3 propagation models, which causes the same limitations previously discussed \cite{5glena,tr38901}.
```

---

# 2.7 Sionna RT

## Put citation after this sentence

```latex
Sionna is a hardware-accelerated differentiable open-source library for research on communication systems \cite{sionna,sionnart}.
```

## Put citation after this sentence

```latex
It is composed of Sionna RT, which is a stand-alone ray tracer for radio propagation modeling, Sionna PHY, and Sionna SYS \cite{sionna,sionnart}.
```

## Put citation after this sentence

```latex
However, it lacks the functionality to simulate the whole 5G NR protocol stack \cite{sionna,sionnart,5glena}.
```

## Put citation after this sentence

```latex
To integrate Sionna RT into ns-3, we leverage pybind11, allowing Sionna RT to live directly within the ns-3 process \cite{pybind11,sionna,sionnart}.
```

---

# 3. Methodology Section: Optional Citation Placement

Your user request mainly asked for Introduction and Background. However, these are also useful places in Methodology.

## Embedded architecture

```latex
The proposed framework embeds Sionna RT inside the ns-3 process through pybind11, avoiding the inter-process communication used by socket-coupled approaches \cite{pybind11,ns3sionna,sionna,sionnart}.
```

## Propagation cache

For your own cache mechanism, cite less. This is your contribution. You can cite channel coherence or beamwidth-related references only if you add a theoretical derivation from literature. Otherwise, no citation is necessary.

## Propagation calculation

```latex
The ray-tracing engine computes site-specific propagation paths, including reflections, diffractions, and propagation delay, from the 3D scene geometry \cite{sionnart,alsamman_mmwave,raymobtime_sionna}.
```

## Energy model

```latex
The energy-aware evaluation is motivated by the strong contribution of radio access networks and base stations to mobile network power consumption \cite{samorzewski_energy}.
```

---

# 4. Quick Rule for Citation Density

Use one citation group per main claim. Avoid adding `\cite{...}` after every sentence. A good paragraph usually has one or two citation groups.

For example:

```latex
Ray tracing is a deterministic channel modeling technique that provides a physically grounded representation of radio signal propagation. It models reflection, diffraction, and scattering from the geometry and materials of a specific environment \cite{alsamman_mmwave,han_thz,raymobtime_sionna}. Compared with stochastic models, this enables more site-specific analysis but increases computational cost.
```

This is better than citing every sentence separately.

---

# 5. Citation Keys Used

The citation keys used in this guide are:

```latex
\cite{sionna}
\cite{sionnart}
\cite{ns3}
\cite{5glena}
\cite{tr38901}
\cite{omnet}
\cite{simu5g}
\cite{ns3sionna}
\cite{pybind11}
\cite{eesm}
\cite{bojovic_mimo}
\cite{bojovic_beamforming}
\cite{raymobtime_sionna}
\cite{alsamman_mmwave}
\cite{han_thz}
\cite{uwaechia_mmwave}
\cite{cazzella_dt_mimo}
\cite{zhou_isac}
\cite{gao_isac_mimo}
\cite{hua_isac_beamforming}
\cite{samorzewski_energy}
```

