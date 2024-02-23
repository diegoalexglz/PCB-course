# Fundamentals

## Definition and fabrication

**PCB:** Print Circuit Board

- **Substratum** (fiberglass)
- **Copper** (conductive part)
- **Solder mask** (humidity and rust protection and soldering quality improvement)

## Technologies

- **Through Hole Technology (THT)**: It's a mounting scheme in which the PCB is drilled and component's pins go through the PCB, so they are soldered at the other end.

- **SMT/ SMD:** It's a superficial mounting scheme in which components are placed on the conductive part, not through it.

## Layers

A double layer PCB has a:

- **Top** layer, coloured in **red**.
- **Screen**, represents the component (position, type, polarization and value), coloured in **yellow**.
- **Bottom** layer, coloured in **blue**.

## Pads

Copper surface in a PCB that allows soldering (or fixing) the component to the board.

## Tracks (Traces)

Copper conductive path that connects pads.

## Vias

Metallic drilling that prevents electric conductivity from interrupting when there are changes in the surfces. They are similar to pads, but vias function as a bridge between layers.

## Types

- Rigid
- Flex
- HDI
- Rigid-Flex

## Design steps

1. Create schematic
2. Map symbols to footprint

## Standards

- IPC 2221 (PCB)
- IPC D 325 (Documentation)
- IPC 2251 (High Frequency PCB)
- IPC 7351 (Footprint)



# Create a project -> Schematic library

1. Click on File -> New -> Project.
2. Write project's name.
3. Set file's path.
4. On the left tab: 'Projects', right click on the project's name.
5. Click on 'add new to project' -> Schematic library.

## Set a snap grid size

1. Click on View -> Grids -> Set snap grid.

## Draw a component

1. Click on 'Place line'

## Access component's properties

1. Double click on the component or shape drawn.

## Rotate a component

1. Press *spacebar* (while component is selected)

## Place a pin

1. Click on 'place pin'

> Note that the cursor will be at one end of the line, that's where the pin is gonna be connected.  Visually, after placed, that end has a 'cross' or '+'.

## Save Schematic Lib and Project files

1. Right click on the 'Schlib' file, in the left tab.
2. Click on save.
3. Right click on the 'Prjpcb' file, in the left tab.
4. Click on save.



# Create a schematic (on existing project)

1. Click on File -> New -> Schematic.

## Add components of  a SchLib to the worksheet

1. Click on 'components' in the upper right corner of the right tab.

2. Click on the selection button.

   > There, we'll see our created library 'Puente de diodos'.

3. Click and place the desired component.

## Wiring

1. Click on 'place wire' or:

```
ctrl + w
```

s 

