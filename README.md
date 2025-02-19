# Crop Plantation Simulation

This is a simple multi-agent simulation of a crop plantation using Pygame. The simulation includes crops, weeds, drones, and tractors, each with specific behaviors and tasks. The environment changes based on the time of day, affecting the temperature and crop growth.

## Features

- **Crops**: Grow over time and can be harvested when matured.
- **Weeds**: Grow faster than crops and need to be removed to prevent them from overtaking the field.
- **Drones**: Can be assigned tasks such as watering or monitoring crops.
- **Tractors**: Can be assigned tasks such as harvesting mature crops or removing weeds.
- **Day-Night Cycle**: The background color changes based on the time of day, simulating a day-night cycle.
- **Temperature**: Changes based on the time of day, affecting crop growth.

## Classes

### Crop
- **Attributes**:
  - `x`, `y`: Position of the crop.
  - `growth_rate`: Rate at which the crop grows.
  - `scale`: Current size of the crop.
  - `matured`: Boolean indicating if the crop is ready for harvest.
- **Methods**:
  - `grow()`: Increases the crop's scale based on its growth rate.

### Weed
- **Attributes**:
  - `x`, `y`: Position of the weed.
  - `growth_rate`: Rate at which the weed grows.
  - `scale`: Current size of the weed.
- **Methods**:
  - `grow()`: Increases the weed's scale based on its growth rate. If the weed grows beyond a certain threshold, it is removed.

### Drone
- **Attributes**:
  - `task`: Current task assigned to the drone (e.g., "water", "monitor").
  - `target_index`: Index of the current target waypoint.
- **Methods**:
  - `update()`: Updates the drone's position and performs its assigned task.
  - `move_along_path()`: Moves the drone along a predefined path.
  - `water_crops()`: Increases the growth rate of nearby crops.
  - `monitor_crops()`: Prints a message indicating that the drone is monitoring crops.

### Tractor
- **Attributes**:
  - `task`: Current task assigned to the tractor (e.g., "harvest").
  - `target_crops`: List of crops targeted for harvesting.
- **Methods**:
  - `update()`: Updates the tractor's position and performs its assigned task.
  - `move_towards_targets()`: Moves the tractor towards the target crops.
  - `harvest_crops()`: Harvests mature crops and removes them from the field.

## Functions

- `generate_crops(spacing)`: Generates a grid of crops with specified spacing.
- `generate_weeds(num_weeds)`: Generates a specified number of weeds at random positions.
- `reset_drone()`: Resets the drone's task and target index.

## Controls

- **Arrow Keys**:
  - **Up**: Decrease the time of day.
  - **Down**: Increase the time of day.
- **Keyboard Keys**:
  - **W**: Assign the watering task to the drone.
  - **M**: Assign the monitoring task to the drone.
  - **H**: Assign the harvesting task to the tractor.

## How to Run

1. Ensure you have Python and Pygame installed.
2. Run the script `multi_agent.py`.
3. Use the controls to interact with the simulation.

## Dependencies

- Python 3.x
- Pygame

## Installation

1. Clone the repository or download the script.
2. Install Pygame using pip:
   ```bash
   pip install pygame
   ```
3. Run the script:
   ```bash
   python multi_agent.py
   ```


## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## Acknowledgments

- Pygame community for the excellent library and documentation.
- Open-source contributors for inspiration and guidance.

---

Enjoy the simulation! 🌱🚜
