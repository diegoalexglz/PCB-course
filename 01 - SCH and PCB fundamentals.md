# CREATE A PROJECT

1. Click on File -> New -> Project.

2. Write project's name.

3. Set file's path.

4. On the left sidebar: 'Projects', right click on the project's name.

5. Click on 'create'



> [!TIP]
>
> Always create a new folder for each new project



> [!TIP]
>
> We can also add **parameters**, like:
>
> *Designer | Alex Alvarez* 
>
> *Start date | 2024*



## Schematic

4. In the left sidebar, right-click on the project and click on **add new to project** -> **schematic**
5. `Ctrl + S`
6. Name the schematic (.SchDoc) as **main**



> [!TIP]
>
> By right-clicking on an empty part of the sheet, we can go to 'project's options' -> 'parameters'.
>
> Also, by opening the 'Properties' right-sidebar we can add more parameters.



### Title Block

7. Right-click on an empty part of the sheet, then select **Place** -> **Text string**
8. On the right-sidebar named 'Properties', write a text.



> [!TIP]
>
> By using `=` we can link the text string to a parameter. For example, for the 'Drawn by: ' cell, we can set the text as '=Designer' or as '=Author'



### Properties sidebar (PS)

While in the 'properties' sidebar, we can:

- Change the **grid units** (mils)
- Select **Enable/disable grid**
- Change **sheet and border color** (white, blue)
- Change **page format**
- Change **page size and orientation** (A3, landscape)
- Select **Enable/disable Title block** (enable, standard)



### Components sidebar (CS)

By default, we have two libraries:

- Miscellaneous devices
- Miscellaneous connectors

There, we can select an element and if we click on `ⓘ` button (it appears by making the sidebar wider), we can see its details, like schematic view, PCB's 2D and 3D views, datasheet, manufacturer, package, pin count, models, etc.



#### Install local library

> [!TIP]
>
> By clicking on `☰` -> 'file-based libraries preferences' -> 'installed', we can add new libraries from our local.



### Upper bar (UB): Selection

In the upper bar, we have some options to select elements inside our sheet.

<img src="images/im_01.png" width="400" style="float: center;">

Note: by pressing `Ctrl + C` we can clear all filters applied by any selection, especially useful after using 'connection', which makes all other elements fade.



### Filters

They can be accesed from the 'properties' sidebar (PS) or from the upper bar (UB).

They let us select specific elements contained in the sheet. For example, if we only wanted to delete wires, we'd have:

<img src="images/im_02.png" width="300" style="float: center;">



------

# FIRST SCH DESIGN

## Place + Shortcuts

When right-clicking on the sheet, we'll see the 'Place' option with the <u>P</u> underlined. That means we can press `P` in the keyboard to access that option. Then, the same happens with the next options in the menu.

**Common shortcuts are:**

<table style="width: 100%; text-align: center; vertical-align: middle; border-collapse: collapse;">
    <thead>
        <tr>
            <th width="50%">Shortcut</th>
            <th width="50%">Action</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>P + P</td>
            <td>Pin</td>
        </tr>
        <tr>
            <td>P + W</td>
            <td>Wire</td>
        </tr>
        <tr>
            <td>P + O</td>
            <td>Power</td>
        </tr>
        <tr>
            <td>P + T</td>
            <td>Text string</td>
        </tr>
        <tr>
            <td>P + D</td>
            <td>Drawing tools</td>
        </tr>
    </tbody>
</table>




### Drawing Tools (and images)

From `P + D` menu, we can use these combinations aswell:

<table style="width: 100%; text-align: center; vertical-align: middle; border-collapse: collapse;">
    <thead>
        <tr>
            <th width="50%">Key</th>
            <th width="50%">Action</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>L</td>
            <td>Line</td>
        </tr>
        <tr>
            <td>U</td>
            <td>Circle</td>
        </tr>
        <tr>
            <td>R</td>
            <td>Rectangle</td>
        </tr>
        <tr>
            <td>G</td>
            <td>Graphic</td>
        </tr>
    </tbody>
</table>

Graphic lets us add a local image.

> [!IMPORTANT]
>
> When placing an image, go to its properties and checkmark the 'Embedded' option, so it is preserved in our project despite deleting the file from our local.




## Rotate an item

By selecting an element in the sheet, we can rotate elements this way:

- Clockwise: `Space`
- Counterclockwise: `Shift + Space`



## Modify Net's colours

A power port is known as a **net** and we can assign a colour to it by clicking it and going to 'preferences' -> 'General (Net)'.

This allows us to see what do we have connected to a certain port.



## Final Sch design 1 (battery)

Steps:

1. Draw a rectangle

2. Place a text string

> [!NOTE]
>
> Another way to do the former is to place a 'text frame' and customize its text, border and fill, instead of drawing a rectangle and then placing a text string.

3. Place a 'Header 2H' connector (from CS)

4. Place a '+5' power port (from UB) and change its name and style (from properties)

5. Place a 'Cap semi' (from CS)

6. Wire everything

7. Modify the '+5V' net colour to red and the 'GND' port to gray

8. Insert a note

9. Create a folder in workspace named 'assets'

10. Insert an image, from the 'assets' folder



> [!WARNING]
>
> Always verify that items fit correctly into the grid. If they don't, reduce the value of 'Snap grid', move the items and restore the default value again.

<img src="images/im_03.png" width="500" style="float: center;">



------

# COMPONENT PROPERTIES

The important properties found in '<u>General</u>' are:

- Designator: it identifies the component. An important element here is the `?` mark, which is known as **annotator**, which AD will later change into a number for the PCB footprint.
- Source: it tells us which library the item belongs to. 

The important properties found in '<u>Parameters</u>' are:

- Value: it's the actual value (in ohms, farads, volts, etc) of the element.



------

# CREATE A CUSTOM COMPONENT

Let's suppose we need to use **LM1117** and we don't have it in AD.



## Setting up the Sch Lib and Doc

First:

1. Create a folder in the project's path named '**docs**'
2. Download the **datasheet** and save it into 'docs' folder
3. Look for important characteristics: pins, input, output, configurations, resistors and capacitors needed, etc.

Then, in AD:

4. Go to 'File' -> New -> Library -> File -> Integrated library

5. Right-click on the new created <u>.LibPkg</u> file and select 'Add new to project' -> 'Schematic library'

**In a Schematic Lib we can create Sch components**.

In the new <u>.SchLib</u> window:

6. Select 'Component_1' from the left sidebar

7. Modify its properties in the right sidebar. For example:

   - Design Item ID: LM1117

   - Designator: U**?**

   - Comment: Linear voltage regulator
   - Description: [copy-paste the datasheet's description]

8. Add <u>Parameters</u>. For example:

   - The datasheet's link
   - The output voltage: 3.3 (**and make it visible**)

9. **Save** both the **.LibPkg** and its child **.SchLib** files with custom names. For example, in this case, we named both as 'myCustomLib'



## Drawing the component

10. The **body**: draw a rectangle

11. Place the **pins**

> [!NOTE]
>
> The *x* end of the line must be facing outwards. This means that we'll have the lines' numbers inside the rectangle.

12. **Rename the pins** to match the datasheet.

It must look like this:

<img src="images/im_04.png" width="350" style="float: center;">



## Adding Lib to the project

In order to be able to use our created component:

13. Go to 'Projects' tab
14. Right-click on the <u>.LibPkg</u> file and click on '**Compile integrated library** myCustomLib.LibPkg' 
15. **Remove the installed library and then, reinstall it (from CS)** as described in [Here](#Install-local-library). (The file to select is <u>myCustomLib.IntLib</u>)



## Adding component to sheet

16. In CS, select the library from the dropdown menu
17. Select the component and place it into the sheet
18. Add every other needed component according to the datasheet (resistors, capacitors, ground ports)



## Final Sch design 2 (power supply)

Following all previous 18 steps, we get this:

<a name="PowerSupply"></a>

<img src="images/im_05.png" width="450" style="float: center;">

------

# CREATE A CUSTOM FOOTPRINT

## Setting up the Pcb Lib

Having created a custom schematic component, 

1. Right-click on 'myCustomLib.LibPkg' -> Add new to project -> PCB library  
2. `Ctrl + S` and save it as '**myCustomLib.PcbLib**'

The project's tree must look like this:

<img src="images/im_06.png" width="250" style="float: center;">

**In a Pcb Lib we can create Pcb footprints**.

Assuming that, from the datasheet, we saw this config and want to use it for the component.

<a name="PinPackage"></a>

<img src="images/im_07.png" width="350" style="float: center;">

Then, in the new <u>.PcbLib</u> window:

3. Select 'PCBComponent_1' from the left sidebar and rename it to, for example '**4-PIN-SOT**'

4. Look for the component's **height** in the datasheet, it must be in the last pages of the document, contained in the 'Mechanical, Packaging, and Orderable Information'.

There, we'll see a header like 'DCY (R-PDSO-G4); PLASTIC SMALL-OUTLINE' and the dimensions, alonside to some notes:

*All linear dimensions are in millimeters (inches).*

<img src="images/im_08.png" width="450" style="float: center;">

5. Set the height in the AD box. In this case, **1.7 mm** (67 mils)

> [!NOTE]
>
> By writing 'mm' after the number, AD will automatically convert the value to mils.

6. Select 'Top overlay' in the lower bar

![image-20240223121114186](./images/im_09.png)

> [!TIP]
>
> By pressing `2` or `3` in keyboard, we can access the 2D and 3D views



## Drawing the component

<img src="images/im_10.png" width="350" style="float: center;">

7. Go to PS and change units to **mm**

### Top overlay: guidance outlines

8. First, draw the **body**. For this:

   - Place a line with `P + L`
   - Press `J + L` and set the **length** (in this case, x=6.7 & y=0)
   - Place another line and set the **width** (in this case, x=6.7 & y=3.7)
   - Select and copy-paste the two lines to get the full body

> [!TIP]
>
> After `Ctrl+C`, AD waits for us to select an starting point to make the copy, we must select the origin (x,y)=(0,0)

What we're trying to achieve with this is merely the outline of the component, as in this picture:

<img src="images/im_11.png" width="350" style="float: center;">

### Top layer: traces andpads

9. Select the 'top layer' in the lower bar.
10. Place the **pads** (pins) from the UB **and set the correct properties**

> [!IMPORTANT]
>
> The pads placed will have a default number, we must make them coincide with the ones from our schematic and the ones in the datasheet. In this case, they are 15, 16 and 17 for VIN, GND and VOUT, respectively. See the [Pins' Sch numbers](#PowerSupply) and the [Pin Package](#PinPackage) images.

- Designator: must be the same number of the pin in the schematic

- Layer: must be 'top layer'

> [!NOTE]
>
> Note that by default, 'Multi-Layer' option is selected, but this means that the pad will have a through-hole in it (THT), which will look like this:
>
> <img src="images/im_12.png" width="100" style="float: center;">
>
> Instead, for this case, we just want a pad, without a hole in it (SMD). So, we select 'top layer' to get this:
>
> <img src="images/im_13.png" width="100" style="float: center;">

- Shape: must coincide with the datasheet. In this case, they are **rectangular**

- Length (under 'pad stack'): must coincide with the datasheet's dimensions (in this case, 1mm & 2.2mm)

- Location (under 'properties'): Move the pads to their correct location. For this, something useful is to change the origin.

#### Change the origin

Go to 'Edit' -> Set Reference -> Location

The shortcut is `Alt + E + F + L`

> [!NOTE]
>
> In AD it's easy to identify the center of a line because the cursor becomes a circle, but, for this example, we need to select 'Top overlay' in order to see it, cause it is where we drew the body.

### Final Pcb design 1 (power supply)

Our Pcb must look like this (body outline is actually yellow if seen while in 'top overlay')

<img src="images/im_14.png" width="250" style="float: center;">

### Linking footprint to Schematic

11. Go back to the SchLib window and click on 'Add footprint' at the bottom bar.
12. Click on 'browse'
13. Select the PCB (in this case, '4-Pin-SOT')
14. `Ctrl+S` to save
15. Compile: Right-click on the <u>.LibPkg</u> file and click on 'Compile integrated lib...' 

Now, we can go to 'main', open CS, select 'myCustomLib' and see the LM1117 both in Schematic and in PCB footprint, like this:

<img src="images/im_15.png" width="250" style="float: center;">

#### Workaround: Component in 'main' was placed before creating footprint  

When we create a component in an SchLib and place it on 'main' sheet, and only after we create the pcb footprint, we'll run into an issue, because the component won't show its footprint.

We can fix this by following this extra steps:

16. Go to 'Tools' -> Footprint manager
17. Select the component (e.g. LM1117)
18. Click on 'add', then 'browse' and select its footprint
19. Click on 'Accept changes (create ECO)', then 'Validate' and finally 'Execute changes' and 'Close'



------

# ANNOTATE DESIGNATORS

If we try to validate our project (right click on '.PrjPcb' -> Validate pcb project) and we still have designators with `?` mark in them, this error will come up:

<img src="images/im_16.png" width="450" style="float: center;">

So, we need to do the following:

1. Go to 'Tools' -> Annotation -> Annotate Sch Quietly (`Alt + T + A + U`)
2. Click 'yes' in the 'Confirm designator changes' popup

After that, our components will have a number assigned, like this:

<img src="images/im_17.png" width="350" style="float: center;">

If we want more control, we can choose 'Annotate schematics' and select the order in which the components are scanned to get a number.

- Up then across
- Down then across
- Across then up
- across then down (default)



------

# CREATE PCB BOARD

## Creating PCB

1. Right-click on '.PrjPcb' file -> Add New to project -> PCB

2. `Ctrl + S` to save it (e.g. myMCU**.PcbDoc**)

**Change origin**

3. Change the origin: 'Edit' -> Origin -> Set (`Alt + E + O + S`)

4. Set the origin in the bottom-left corner of the PCB

**Change size: the Keep Out Layer**

5. Select keep-out-layer (KOL).

   The KOL is always used when we are working with non-physical things to be put in the PCB.

6. Draw a rectangle with lines.

> [!TIP]
>
> By pressing `Tab` we can pause the view (zoom, movement) to set the line width and the layer more comfortably.

7. Select all the lines of the rectangle (it can be done by clicking on one and then pressing `Tab`)  and go to 'Design' -> Board shape -> Define board shape from selected objects (`Alt + D + S + D `)

If a 'Couldn't find... use primitive edges instead?' box pops up, it's because we haven't selected all the lines, which means we have an open outline.



## Adding Sch Comp to PCB	

8. Go to 'main' and verify that all comps designators are annotated

9. Go to 'Design' -> 'Update PCB... myMCU.PcbDoc' (`Alt + D + U`)

10. Validate and execute changes

We'll see our comps' footprints in the PCB enclosed by a rectangular area, known as a **room**. It's a good practice to keep it.

<img src="images/im_18.png" width="550" style="float: center;">

11. (Optional) Modify the designators styles (font, size)

> [!NOTE]
>
> Now, let's notice something. If seen from afar, we'll see come colours. For example, for capacitors C1, C2 and C3 we have red, green and gray, which are the colours of their nets (5.5V, 3.3V and GND, respectively).
>
> But, if we zoom, we can see that those colours are mixed with other colours, the latter being the ones that help us identify which layer the objects belong to.
>
> <img src="images/im_19.png" width="450" style="float: center;">
>
> To avoid this,
>
> 1. Go to 'main'
>
> 2. Go to 'View' -> Set net colours -> Clear all net colours
>
> 3. Go to 'Design' -> 'Update PCB... myMCU.PcbDoc' (`Alt + D + U`)
>
> 4. Validate and execute changes
>
> Now, we can go back to PCB and see the layer colours.
>
> - **Top layer:** red
> - **Top overlay:** yellow
> - **Top solder:** purple
> - **Multi layer:** gray
>
> <img src="images/im_20.png" width="450" style="float: center;">



> [!TIP]
>
> By dragging an object with the mouse, we can see which are the connections (these tiny lines) that it has with another object by moving them closer.



> [!WARNING]
>
> If a component gets coloured in green, it means an error.
>
> Up until this point, it can possibly be because the comp is outside the room or outside the keep-out-layer lines.
>
> <img src="images/im_21.png" width="200" style="float: center;">



### Highlight Footprint: Cross Probe

To highlight a component's footprint in the PCB by selecting the component in the SCH, we can:

1. Go to 'Tools' -> Cross Probe (`Alt + T + C`)
2. Click on the component (in the SCH)
3. Right-click on a blank space

Then, when we switch back to the PCB window, we'll see that comp's footprint highlighted with a filter.



### Select Footprint: Cross select

<a name="CrossSelect"></a>

Similarly, to select a component's footprint in the PCB by selecting the component in the SCH, we can:

1. Go to 'Tools' -> Cross select mode (`Ctrl + Shift + X`)
2. Click on the component (in the SCH)

Then, when we switch back to the PCB window, we'll see that comp's footprint selected.



## Arranging the comps in the PCB

### Precise movement

After selecting an object, we can use `Ctrl +` `↑ ↓ → ←` to move it with precision. The movement distance can be modified by pressing `G` and selecting a different value.



### Allign vertical centers

To allign objects,

1. Select them
2. Press `Shift + A + V`
3. Click on the object that will remain in its same position



### Detect proximity errors

When there are two comps too close to each other, they will turn green. To see what's the error, we can press `Shift + V`.



### Reposition footprints in order

When having the [Cross-select](#CrossSelect) option **on**, we can also use **a second tool**, which allows to move each footprint from the objects we previously selected in SCH, in the order they were selected. 

(While in .PcbDoc)

1. Go to 'Tools' -> Comp placement -> Reposition selected comps (`Alt + T + O + C`)



## Routing

Going back to our original steps for creating a PCB board,

12. Use 'Interactively route connections' (`Ctrl + W`) from the UB to draw a line across the components.
12. Change the trace's width



> [!WARNING]
>
> By default, the line's width is 10mil. If we make it any wider, e.g. 11 mil, it will turn green, as if an error. But it's not really an error. That happens due to a rule.
>
> To change it:
>
> 1. Go to 'Design' -> Rules (`Alt + D + R`)
>
> 2. Go to 'Routing' -> Width
>
> There, we'll see a solo rule that states a min and max width for all traces of 10mil.
>
> 3. Change the width restrictions to the desired ones
>
> Now we can go back to PCB and the errors in the traces will have dissapeared.



> [!TIP]
>
> From experience, when having a THT Comp (like the Header 2H pins), its soldering can ruin the pads and traces that are connected with it if the traces are not wide enough. So, we should **try to make the trace as wide as we can** (depending on the width of the other Comps).
>
> In this case, for example, we should check on the capacitor pads' width, which turns out to be 43 mil:
>
> <img src="images/im_22.png" width="500" style="float: center;">
>
> And then create our trace with a 43mil width, and it will look like this:
>
> <img src="images/im_23.png" width="400" style="float: center;">



## Final Pcb 1 (battery + power supply)

14. Once routing is done, modify the room's dimensions and the KOL lines to make the PCB smaller and make it fitting to the space our comps use.

Our final result is:

**In 2D**

<img src="images/im_24.png" width="600" style="float: center;">

**In 3D**

<img src="images/im_25.png" width="400" style="float: center;">