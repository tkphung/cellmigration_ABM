# cellmigration_ABM
This agent-based model (built in [NetLogo](https://ccl.northwestern.edu/netlogo/)) simulates cell migration into an empty wound space. The HTML version was generated using *NetLogo Web*.

### SETUP SIMULATION
Click **setup** (at the bottom of the interface) to initialize cells in the wound environment. The *SETUP SIMULATION* section includes adjustable initial conditions:

- Number of cells
- Whether to include *cytokine*?
	- Amount of *cytokine* starting in the wound

### CELL SENSING OPTIONS
These options determine how the cells determine their *speed* and orientation of migration.

**Speed** is determined by two competing signals:

- Speed increases in less crowded areas (lower *localdensity*)
	- *localdensity* is a count of all cells within a circle around the cell determined by the **sense-radius** slider
	- increasing **sense-radius** increases "how far the cell senses neighbors"
- Speed increases in the presence of *cytokine*

The **cytokine-bias** slider determines which signal is more heavily weighted.


**Orientation** of migration is random unless the **toward-cytokine** flag is *ON*.

### RUN SIMULATION
After clicking **setup**, click **go** to run the simulation. 

The **draw-paths** flag can be turned *ON* at any point to trace the migration paths.


## THINGS TO NOTICE

The plots to the right of the simulation window include

- Average migration *speed* of all of the cells- this gives a sense of how much migration is occuring
- Average *localdensity* of all the cells- this is a metric of how "crowded" the cells feel
- Average y-coordinate of all the cells- this is a metric of how far into the wound the cells have migrated

## THINGS TO TRY
For a simulation, if the parameter is not listed, it does not matter what value is set.


### Single-cell random walk
Observe a single cell migrating

**number-cells** = 1

**wound-cytokine** = Off

**cytokine-bias** = 0%

**toward-cytokine** = Off

**draw-paths** = On


**setup** + **go**


### Cell density jamming
This simulation looks at the effect of the **sense-radius** on determining cell migration speed.

**number-cells** **~300**

**wound-cytokine** = Off

**cytokine-bias** = 0%

**sense-radius** = **10**

**toward-cytokine** = Off


**setup** + **go**

- Where are cells moving the most?

- **Decrease the sense-radius by moving the slider left.**
	- *Turn off draw-paths if the frame is too busy**
	- What happens to the average speed of the cells?
	- Do cells move into the wound region?


### Chemotaxis
This simulation first shows what happens when cell migration *speed* is determined by *cytokine*. Then it shows the influence of a "directed migration" through chemotaxis.

**number-cells** ~300

**wound-cytokine** = **On**

**cytokine-bias** = **100%**

**toward-cytokine** = Off


**draw-paths** = On

**setup** + **go**

- *Where* and *when* are cells moving the most?
	- How does the leading edge of the wound compare to the regions further back?

- **Switch toward-cytokine to On**
	- What happens? (Look at the Average Speed and Wound Infiltration plots)
	- Do cells move into the wound region?


### Mixed Signals
This simulation sets *speed* based on cell crowding and orientation of migration based on *cytokine*.

**number-cells** ~300

**wound-cytokine** = On

**cytokine-bias** = **0%**

**sense-radius** = **10**

**toward-cytokine** = **On**


**draw-paths** = On

**setup** + **go**

- *Where* and *when* are cells moving the most?
	- How does the leading edge of the wound compare to the regions further back?

- How does the migration patterns compare to the previous "CHEMOTAXIS" simulation?
	- **Slide the cytokine-bias towards 100%**
	- What happens to the migration?



## EXTENDING THE MODEL

This model only considers migration based on chemotaxis and "cell density".

### Discussion Questions
- What other biological processes might be interesting to add to this simulation?
	- Other interactions between agents+patches?
- What are some limitations of an agent-based modeling platform?
- Each simulation is unique, how do we gain helpful insight from these models?

Created by Thien-Khoi N. Phung (@tkphung, tkphung@hsph.harvard.edu)
