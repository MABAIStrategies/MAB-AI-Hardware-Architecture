# MAB AI Hardware Architecture

> A web app that recommends the most optimized hardware architecture for a given use case.

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)  <!-- TODO: confirm against LICENSE -->

Maintained by [MAB AI Strategies LLC](https://mabaistrategies.com).

---

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [How It Works](#how-it-works)
4. [Getting Started](#getting-started)
5. [Usage](#usage)
6. [Project Structure](#project-structure)
7. [Configuration](#configuration)
8. [Roadmap](#roadmap)
9. [Contributing](#contributing)
10. [License](#license)
11. [Contact](#contact)

---

## Overview

Choosing hardware for AI workloads (local LLM inference, fine-tuning, agent
pipelines, edge deployment) means balancing cost, VRAM, memory bandwidth,
power draw, compatibility, and availability. This tool takes a use case
as input and returns the hardware architecture that best fits it.

**Typical questions it answers**
- What GPU/CPU/RAM configuration runs a 70B-parameter model at usable speed?
- Is a refurbished workstation or a cloud instance cheaper for my workload?
- What is the minimum viable build for a multi-agent automation stack?

## Features

- Use-case-driven recommendations (inference, training, agents, edge, general compute)
- Side-by-side comparison of candidate architectures
- Optimization across cost, performance, power, and compatibility
- Runs in the browser, with no backend required for the core experience  <!-- TODO: verify -->
- Desktop updater helper (`desktopupdater.html`)  <!-- TODO: describe -->

## How It Works

1. **Define the use case.** Select the workload type, model size, concurrency, and budget.
2. **Set constraints.** Choose power limits, form factor, new vs. refurbished, and local vs. cloud.
3. **Score candidates.** Each architecture is scored against weighted criteria.
4. **Review the recommendation.** The top-ranked build is shown with trade-offs and alternatives.

| Criterion        | Description                                      |
|------------------|--------------------------------------------------|
| Performance      | Throughput / tokens per second for the workload  |
| Memory fit       | VRAM and system RAM versus model requirements    |
| Cost             | Upfront and ongoing (power, cloud) cost          |
| Compatibility    | Driver, framework, and OS support                |
| Availability     | Current market and supply considerations         |

<!-- TODO: replace with the actual scoring logic -->

## Getting Started

### Prerequisites

- A modern browser (Chrome, Edge, Firefox, Safari)
- Git
- Optional: Node.js 18+ or Python 3.10+ for a local static server

### Installation

```bash
git clone [https://github.com/MABAIStrategies/MAB-AI-Hardware-Architecture.git](https://github.com/MABAIStrategies/MAB-AI-Hardware-Architecture.git)
cd MAB-AI-Hardware-Architecture
```

### Run locally

Open the HTML file directly:

```bash
open desktopupdater.html        # macOS
start desktopupdater.html       # Windows
xdg-open desktopupdater.html    # Linux
```

Or serve it over HTTP:

```bash
python -m http.server 8080
# then visit http://localhost:8080
```

## Usage

1. Open the app in your browser.
2. Pick a use case and enter your constraints.
3. Review the ranked architectures and export or save the result.  <!-- TODO: confirm export -->

## Project Structure
