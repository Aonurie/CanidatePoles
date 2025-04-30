# CanidatePoles

---
title: "Energy Grid Canidate Poles"
description: "A Python toolkit creating canidate poles using ILP."
---

export const PropsTable = ({ props }) => <table>{/* ... */}</table> {/* Example MDX component import placeholder */}

# Energy Grid Pole Placement Optimization

This repository provides a Python-based toolkit for optimizing the placement of utility poles and cabling in an energy grid. It reads building and power source coordinates from a CSV file, generates candidate pole locations, enforces graph-based distance constraints, connects buildings to poles, calculates cost, and visualizes the resulting network.

## Features

- **Candidate Pole Generation**: Uses a grid-based set cover formulation with integer linear programming (PuLP) to find a minimal set of poles covering all buildings within a specified radius.
- **Pole Distance Enforcement**: Constructs a Minimum Spanning Tree (MST) over poles and the power source, automatically adding intermediate poles where segment lengths exceed a maximum distance.
- **Building-to-Pole Connections**: Attaches each building to its nearest pole using Haversine distances on Earth's surface.
- **Cost Calculation**: Computes total cost based on user-defined per-unit costs for poles, low-voltage (LV) cable segments (≤30 m), and medium-voltage (MV) cable segments (>30 m).
- **Visualization**: Provides Matplotlib-based scatter plots of buildings, poles, power source, and network edges.

## Prerequisites

- **Python** 3.7 or higher

### Dependencies

Install required packages with:

```bash
pip install -r requirements.txt
