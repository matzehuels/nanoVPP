# nanoVPP
The simplest, fastest repository for demonstrating Virtual Power Plants. Inspired by Andrej Karpathy's [nanoGPT](https://github.com/karpathy/nanoGPT).

## What is a Virtual Power Plant?
A Virtual Power Plant (VPP) is a managed network that aggregates and coordinates multiple distributed energy resources (DERs) to function as a single power plant. A VPP may consists of:
- **Solar PV Systems**: Residential and commercial rooftop solar installations
- **Battery Storage**: Both utility-scale and residential battery systems
- **Electric Vehicles**: Connected EVs that provide vehicle-to-grid services
- **Smart Loads**: Controllable loads like smart thermostats or water heaters

These distributed resources are orchestrated through software that optimizes their collective control, enabling them to provide grid services (frequency regulation, demand response) or to generate revenue through energy market participation.

## Why nanoVPP?
Just like nanoGPT strips away the complexity to teach core transformer concepts, nanoVPP provides a minimal implementation of VPP control algorithms. We focus on simple, readable Python code with minimal dependencies, clear documentation, and real-world examples using publicly available data.

## Device Models
To demonstrate VPP control algorithms, we implement simple state space models for common DER types:
- **Battery Storage**: First-order state space model with SoC dynamics and power constraints
- **Building HVAC**: Second-order RC thermal model with temperature state dynamics
- **EV Charging**: Queue-based model for charging stations with arrival/departure distributions
- **Solar PV**: Clear sky model with weather-based derating

These models provide a lightweight simulation environment for testing VPP control strategies.

## Use Cases
We'll implement simple control algorithms for some common VPP use cases that we can simulate in our environment:

- **Peak Shaving**: Reduce grid demand during critical peak hours by using a PID controller with cascaded asset dispatch

- **Grid Frequency Response**: Provide rapid power adjustments to maintain grid frequency using droop control with rate limiting

- **Renewable Integration**: Maximize renewable energy utilization by applying receding horizon control with load shifting

- **Market Participation**: Optimize VPP resources for price arbitrage using dynamic programming and the Bellman equation
