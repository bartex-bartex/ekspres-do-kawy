# Coffee Machine – Real-Time System Design in AADL

## Authors

- Bartosz Warchoł, bwarchol@student.agh.edu.pl  
- Piotr Waluszek, waluszekp@student.agh.edu.pl

## Project Description

The coffee machine is a real-time system designed in the AADL language, aimed at enabling the user to prepare various types of coffee. The system manages the intake of water, coffee, and milk, the milk frothing process, grinding coffee beans, and temperature control.

## System Components

### Package

- **CoffeeMachine** – the main package integrating all system components.

### Main Systems
| System Name               | Description                                     |
|--------------------------|--------------------------------------------------|
| `CoffeeProductionSystem` | Top-level system integrating all subsystems     |
| `CoffeeMachineSystem`    | Subsystem: Handles coffee production and brewing           |
| `IO_monitoringSystem`    | Subsystem: Manages sensors and user interface              |

### Processors
| Processor Name    | Description                              | System                   |
|------------------|------------------------------------------|--------------------------|
| `MainController` | Main CPU for CoffeeMachineSystem         | CoffeeMachineSystem     |
| `IOController` | Main CPU for IO_monitoringSystem         | IO_monitoringSystem     |
| `BrewingController` | Top-level CPU for overall coordination   | CoffeeProductionSystem  |

### Buses
| Bus Name    | Description                                          |
|-------------|------------------------------------------------------|
| `MainDataBus`   | Main system bus connecting components                |
| `DataBusBrewing`   | Local bus for CoffeeMachineSystem                   |
| `DataBusIO`   | Local bus for IO_monitoringSystem                   |

### Memory
| Memory Name     | Description                                     |
|-----------------|------------------------------------------------|
| `SystemMemory`  | Shared memory for all system components         |

## Devices

| Device              | Description                          |
|---------------------|--------------------------------------|
| `AmountSensor`      | Measures coffee quantity.            |
| `TemperatureSensor` | Measures temperature.                |
| `WaterPump`         | Controls water flow.                 |
| `MilkPump`          | Controls milk flow.                  |
| `CoffeeDispenser`   | Dispenses brewed coffee.             |
| `CoffeeGrinder`     | Activates the coffee grinder.        |
| `MilkDispenser`     | Dispenses milk.                      |
| `MilkFrother`       | Froths the milk.                     |
| `WaterHeater`       | Heats water.                         |
| `MilkHeater`        | Heats milk.                          |
| `LCDDisplay`        | Displays messages to the user.       |

## Threads

| Thread                   | Description                                                    |
|--------------------------|----------------------------------------------------------------|
| `AmountControl`          | Processes data from `AmountSensor`.                            |
| `TempControl`            | Processes data from `TemperatureSensor`.                       |
| `WaterPumpControl`       | Controls the `WaterPump`.                                      |
| `MilkPumpControl`        | Controls the `MilkPump`.                                       |
| `WaterHeaterControl`     | Controls the `WaterHeater`.                                    |
| `MilkHeaterControl`      | Controls the `MilkHeater`.                                     |
| `CoffeeDispenserControl` | Controls the `CoffeeDispenser`.                                |
| `CoffeeGrinderControl`   | Controls the `CoffeeGrinder`.                                  |
| `MilkDispenserControl`   | Controls the `MilkDispenser`.                                  |
| `MilkFrotherControl`     | Controls the `MilkFrother`.                                    |
| `IngredientsControl`     | Maps beverage requirements to actuator commands.               |
| `DispenseControl`        | Coordinates final dispensing of milk and coffee.               |
| `BrewingControl`         | Handles top-level beverage preparation and display output.     |
| `TemperatureControl`     | Periodically evaluates and controls temperature regulation.     |

## Processes

| Process              | Role                                     |
|----------------------|------------------------------------------|
| `SensorDataProcess`  | Acquires and formats sensor input.       |
| `BrewingProcess`     | Main logic for coffee beverage preparation. |

## System Features

- **Support for multiple beverage types** – espresso, latte, cappuccino, and customizable strength and milk foam density.
- **Parameter personalization** – water amount, coffee amount, milk amount, temperature, frothing option, coffee strength, foam density.
- **Monitoring** – water level, milk level, temperature.

## Images

### System Overview
![Big Picture View](big_picture.svg)
*High-level architecture diagram showing main system components and their interactions*

### Detailed System Architecture
![Full System View](full_view.svg)
*Detailed view of all system components including threads, processes, buses, and data flows*