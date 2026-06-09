# Mesa Examples
## Core Mesa examples
The core Mesa examples are available at the main Mesa repository: https://github.com/mesa/mesa/tree/main/mesa/examples

Those core examples are fully tested, updated and guaranteed to work with the Mesa release that they are included with. They are also included in the Mesa package, so you can access them directly from your Python environment.

## Mesa user examples
This repository contains user examples and showcases that illustrate different features of Mesa. For more information on each model, see its own README and documentation.

- Mesa examples that work on the Mesa and Mesa-Geo main development branches are available here on the [`main`](https://github.com/mesa/mesa-examples) branch.
- Mesa examples that work with Mesa 3.x releases are available here on the [`mesa-3.x`](https://github.com/mesa/mesa-examples/tree/mesa-3.x) branch.
- Mesa examples that work with Mesa 2.x releases and Mesa-Geo 0.8.x releases are available here on the [`mesa-2.x`](https://github.com/mesa/mesa-examples/tree/mesa-2.x) branch.

To contribute to this repository, see [CONTRIBUTING.rst](https://github.com/mesa/mesa-examples/blob/main/CONTRIBUTING.rst).

This repo also contains a package that readily lets you import and run some of the examples:
```console
$ # This will install the "mesa_models" package
$ pip install -U -e git+https://github.com/mesa/mesa-examples#egg=mesa-models
```
For Mesa 3.x examples, install:
```console
$ # This will install the "mesa_models" package
$ pip install -U -e git+https://github.com/mesa/mesa-examples@mesa-3.x#egg=mesa-models
```
For Mesa 2.x examples, install:
```console
$ # This will install the "mesa_models" package
$ pip install -U -e git+https://github.com/mesa/mesa-examples@mesa-2.x#egg=mesa-models
```
```python
from mesa_models.boltzmann_wealth_model.model import BoltzmannWealthModel
```
You can see the available models at [setup.cfg](https://github.com/mesa/mesa-examples/blob/main/setup.cfg).

Table of Contents
=================

* [Repository Layout](#repository-layout)
* [How to choose an example](#how-to-choose-an-example)
* [Example Catalog](#example-catalog)
  * [Core Mesa Examples](#core-mesa-examples)
  * [GIS Examples](#gis-examples)
  * [Reinforcement Learning Examples](#reinforcement-learning-examples)
* [Feature Index](#feature-index)
* [Maintainer Notes](#maintainer-notes)

## Repository Layout

This repository is organized by broad implementation area:

| Directory | Purpose |
| --- | --- |
| [`examples/`](examples) | General Mesa examples, including grid, network, visualization, discrete-event, economic, social, and cellular automata models. |
| [`gis/`](gis) | Mesa-Geo examples that use vector data, raster data, or raster/vector overlays. |
| [`rl/`](rl) | Reinforcement-learning examples that wrap Mesa models as learning environments. |

The categories below are intended as a navigation aid, not as mutually exclusive filesystem folders. For example, a model can be both a grid-space example and a visualization example. When adding an example, keep it in the appropriate top-level directory and add it to the catalog and feature index below.

## How to choose an example

- New to Mesa agent-based modeling? Start with [Bank Reserves](examples/bank_reserves), [Color Patches](examples/color_patches), or [Forest Fire](examples/forest_fire).
- Interested in modern Mesa spaces and property layers? See [Game of Life Fast](examples/conways_game_of_life_fast) or [Hexagonal Ant Foraging](examples/hex_ant).
- Interested in networks? See [Boltzmann Wealth Model with Network](examples/boltzmann_wealth_model_network), [Ant System for TSP](examples/aco_tsp), or [Dining Philosophers](examples/dining_philosophers).
- Interested in geospatial models? Start with [GeoSchelling](gis/geo_schelling), then compare the raster examples such as [Rainfall](gis/rainfall) and [Urban Growth](gis/urban_growth).
- Interested in reinforcement learning? Start with the [`rl/` README](rl/README.md), then explore [Wolf-Sheep](rl/wolf_sheep), [Epstein Civil Violence](rl/epstein_civil_violence), or [Boltzmann Money](rl/boltzmann_money).

## Example Catalog

### Core Mesa Examples

| Example | Path | Description |
| --- | --- | --- |
| Bank Reserves Model | [`examples/bank_reserves`](examples/bank_reserves) | Simplified economy where people trade, save, borrow, and interact with a bank reserve system. Demonstrates grid agents, data collection, sliders, visualization, inheritance, and batch runs. |
| Color Patches | [`examples/color_patches`](examples/color_patches) | Cellular automaton where agents update opinions based on neighbors, creating expanding and disappearing opinion patches. |
| Conway's Game of Life Fast | [`examples/conways_game_of_life_fast`](examples/conways_game_of_life_fast) | Vectorized Game of Life implementation using NumPy/SciPy for high-performance cellular automata and simple Solara visualization. |
| Hexagonal Snowflake | [`examples/hex_snowflake`](examples/hex_snowflake) | Conway-style growth model on a hexagonal grid. |
| Hexagonal Ant Foraging | [`examples/hex_ant`](examples/hex_ant) | Ant foraging model on a toroidal `HexGrid` using property layers for food, home, obstacles, and pheromones. |
| Forest Fire | [`examples/forest_fire`](examples/forest_fire) | Cellular automaton of fire spreading through a forest, based on the NetLogo Fire model. |
| Hotelling's Law | [`examples/hotelling_law`](examples/hotelling_law) | Market competition model where stores adjust price and location while consumers choose among stores. |
| Emperor's Dilemma | [`examples/emperor_dilemma`](examples/emperor_dilemma) | Social-norm model showing how public compliance and enforcement can persist even when many agents privately reject the norm. |
| Humanitarian Aid Distribution | [`examples/humanitarian_aid_distribution`](examples/humanitarian_aid_distribution) | Needs-based behavioral architecture where aid trucks triage and deliver water/food to beneficiaries with dynamic urgency states. |
| Rumor Mill | [`examples/rumor_mill`](examples/rumor_mill) | Rumor-spreading model adapted from NetLogo, controlled by spread chance and initial knowing percentage. |
| Axelrod Culture | [`examples/axelrod_culture`](examples/axelrod_culture) | Cultural dissemination model where neighboring agents interact based on similarity and can form stable cultural regions. |
| Deffuant-Weisbuch | [`examples/deffuant_weisbuch`](examples/deffuant_weisbuch) | Bounded-confidence opinion dynamics model with continuous opinions, pairwise interactions, and Solara plots. |
| Boltzmann Wealth Model with Network | [`examples/boltzmann_wealth_model_network`](examples/boltzmann_wealth_model_network) | Wealth exchange model implemented on a network grid, producing a skewed wealth distribution over time. |
| Ant System for Traveling Salesman Problem | [`examples/aco_tsp`](examples/aco_tsp) | Ant-colony optimization model for TSP using a network representation, pheromone trails, and heuristic city proximity. |
| Dining Philosophers | [`examples/dining_philosophers`](examples/dining_philosophers) | Classic synchronization/resource-contention problem modeled on a network graph. |
| Charts | [`examples/charts`](examples/charts) | Visualization-focused example showing Mesa chart components using a modified Bank Reserves model. |
| Shape Example | [`examples/shape_example`](examples/shape_example) | Minimal visualization example with shaped agents and text overlays. |
| M/M/c Queue | [`examples/mmc_queue`](examples/mmc_queue) | Pure discrete-event simulation of a multi-server FIFO queue with analytical validation. |
| El Farol | [`examples/el_farol`](examples/el_farol) | Restaurant attendance model where agents decide whether to attend based on memory and reward. |
| Schelling with Caching and Replay | [`examples/caching_and_replay`](examples/caching_and_replay) | Demonstrates recording, persisting, and replaying simulation runs with Mesa-Replay. |
| Termites | [`examples/termites`](examples/termites) | Decentralized termite/wood-chip model showing emergent pile formation from simple local rules. |
| Virus-Antibody | [`examples/virus_antibody`](examples/virus_antibody) | Immune-response model with viruses, antibodies, memory sharing, mutation, and divergent outcomes from small parameter changes. |
| Warehouse | [`examples/warehouse`](examples/warehouse) | Meta-agent example where warehouse robots are composed of sub-agents such as sensors, routers, and workers. |

### GIS Examples

| Example | Path | Data type | Description |
| --- | --- | --- | --- |
| GeoSchelling Model (Polygons) | [`gis/geo_schelling`](gis/geo_schelling) | Vector polygons | Schelling-style segregation model using NUTS-2 regions as polygon GeoAgents in a GeoSpace. |
| GeoSchelling Model (Points & Polygons) | [`gis/geo_schelling_points`](gis/geo_schelling_points) | Vector points and polygons | GeoSchelling variant that combines point agents with polygon geography. |
| GeoSIR Epidemics Model | [`gis/geo_sir`](gis/geo_sir) | Vector points and polygons | Epidemic model with person agents and Toronto neighborhood hotspot polygons. |
| Agents and Networks | [`gis/agents_and_networks`](gis/agents_and_networks) | Vector/network | Mesa-Geo example combining geospatial agents with network structure. |
| Rainfall | [`gis/rainfall`](gis/rainfall) | Raster | Rainfall and runoff model where raindrops move over an elevation raster. |
| Urban Growth | [`gis/urban_growth`](gis/urban_growth) | Raster | Urban-growth model using raster land-use dynamics. |
| Population | [`gis/population`](gis/population) | Raster and vector overlay | Population model combining raster population data and vector agents. |

### Reinforcement Learning Examples

| Example | Path | Description |
| --- | --- | --- |
| Boltzmann Money RL | [`rl/boltzmann_money`](rl/boltzmann_money) | PPO-based experiment that trains agents in a Boltzmann wealth environment to reduce inequality. |
| Epstein Civil Violence RL | [`rl/epstein_civil_violence`](rl/epstein_civil_violence) | Multi-agent RL environment for the Epstein civil violence model with citizen and police policies. |
| Wolf-Sheep RL | [`rl/wolf_sheep`](rl/wolf_sheep) | Multi-agent predator-prey RL environment with wolf, sheep, and grass dynamics. |

## Feature Index

Use this index when you know what Mesa feature or modeling pattern you want to learn.

| Topic | Examples |
| --- | --- |
| Grid / cellular automata | [Bank Reserves](examples/bank_reserves), [Color Patches](examples/color_patches), [Game of Life Fast](examples/conways_game_of_life_fast), [Hexagonal Snowflake](examples/hex_snowflake), [Forest Fire](examples/forest_fire), [Termites](examples/termites) |
| Hex grids and property layers | [Hexagonal Ant Foraging](examples/hex_ant), [Hexagonal Snowflake](examples/hex_snowflake) |
| Networks | [Boltzmann Wealth Model with Network](examples/boltzmann_wealth_model_network), [Ant System for TSP](examples/aco_tsp), [Dining Philosophers](examples/dining_philosophers) |
| Continuous or non-grid dynamics | [Virus-Antibody](examples/virus_antibody), [Deffuant-Weisbuch](examples/deffuant_weisbuch) |
| Social / opinion / culture dynamics | [Axelrod Culture](examples/axelrod_culture), [Deffuant-Weisbuch](examples/deffuant_weisbuch), [Emperor's Dilemma](examples/emperor_dilemma), [Rumor Mill](examples/rumor_mill), [El Farol](examples/el_farol) |
| Economics / operations / markets | [Bank Reserves](examples/bank_reserves), [Boltzmann Wealth Model with Network](examples/boltzmann_wealth_model_network), [Hotelling's Law](examples/hotelling_law), [M/M/c Queue](examples/mmc_queue) |
| Visualization patterns | [Charts](examples/charts), [Shape Example](examples/shape_example), [Game of Life Fast](examples/conways_game_of_life_fast), [Hotelling's Law](examples/hotelling_law) |
| Discrete-event simulation | [M/M/c Queue](examples/mmc_queue) |
| Caching / replay | [Schelling with Caching and Replay](examples/caching_and_replay) |
| Meta-agents / agent composition | [Warehouse](examples/warehouse) |
| Humanitarian / health | [Humanitarian Aid Distribution](examples/humanitarian_aid_distribution), [Virus-Antibody](examples/virus_antibody), [GeoSIR](gis/geo_sir) |
| GIS vector data | [GeoSchelling](gis/geo_schelling), [GeoSchelling Points](gis/geo_schelling_points), [GeoSIR](gis/geo_sir), [Agents and Networks](gis/agents_and_networks) |
| GIS raster data | [Rainfall](gis/rainfall), [Urban Growth](gis/urban_growth), [Population](gis/population) |
| Reinforcement learning | [Boltzmann Money RL](rl/boltzmann_money), [Epstein Civil Violence RL](rl/epstein_civil_violence), [Wolf-Sheep RL](rl/wolf_sheep) |

## Maintainer Notes

- Keep local example documentation named `README.md` for consistency across platforms and tooling.
- Add every new example directory to the catalog above, even if it also appears in the feature index.
- Prefer tagging examples in the feature index over moving directories to force a single-category hierarchy.
- If an example has extra dependencies, document them in that example's `README.md` and, when appropriate, in a local `requirements.txt`.
