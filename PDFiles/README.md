# INPUT FILES for PHYSICAL DESIGN(PD)
## 1. Liberty Files (.lib)
### Provides functionality and timing information for standard cells and macros.
- Soft and Hard Macros: Functionality nad timing details.
- Standard Cell Internal Delays
- Noise Margin Secifications.
- PVT Conditions(Process, Voltage, Temperature).
- Input Slew and output load values
- Leakage Power Information
- Pin direction and Pin capacitance
- Rise and Fall Time constrints
- Pulse Width requirements
## 2. Synopsys Design Constraints (.sdc)
### Defines timing constraints and exceptions.
- Clock Constraints: Primary clocks, virtual clocks, generated clocks.
- Timing Constraints: Input/Output Delays, Multicycle Path, False path, set case analysis, set disable analysis, max/min delay.
- Input Transition & Output Load specifications
- Group Path contraints
- Uncertainities(Jitter, Clock Uncertainty).
- Latencies & Targets(Clock/ Source/ Netwrok Latency)
- Max Transition & Max Capacitance Targets.
## 3. Netlist(.v)
### Describes the logical structure of the design
- Textual Decription of instantiated standard cells/macros
- Logical connectivity of cells and modules
- Flops & Registers Collection
- Cell Attributes(drive strength, function, etc.)
## 4. Library Exchange Format(.lef)
### Defines the physical layout information of standard cells and macros
- Number of metal layers and metal layer specifications.
- Pin details: Name, location, direction, shape, Layer, symmetry.
- Metal Width specifications for routing
## 5.  Technology File(.tf)
## Specifies metal layer rules and characteristics
- Design Rules for routing and placement
- Via information(dimensions, spacing).
- ERC & LVS Rules (Electrical Rule check & Layout vs. Schematic).
- Antenna Ratio & Max Current Density constraints
## 6.TLU + File(.tluplus)
## Generated from ITF files and used for parastic extraction
- Wire capacitance values
- Net length and Spacing Information
- RC Parasitic Models for different process corners
## 7. Specification File(.spec)
## Contains special constraints for physical design
- Non-Default Rules(NDR).
- CTS(Clock Tree Synthesis) Exceptions: Exclude pin, ignore pin, float pin, nono-stop pin, sink pin.
- Skew & Latency Targets
- Uncertainties
- Max/Min metal layers for Clock Routing
- Clock inverters and buffers selection during CTS.
## 8. MMMC File(Multi-mode multi Corner)
##Defines operating conditions for different process scenarios.
- PVT Corners: Multiple process, voltage, and temperature conditions.
- RC Delays for Different Corners.
- Operating Modes(e.g., functional mode, test mode, etc).
## 9. Unified Power Format(.upf)
## Specfies the power intent of the design.
- Power Distribution Architecture(Power Domains)
- Power Strategies(Retention, Isolation, Shutoff).
- Power State Tables.
- Operating Voltages for differnt domains.
- Special Power Cells: Level shifters, Isolation cells, Retention Cells, Power switches.
## 10. Scan Definition File (.scandef)
##Defines scan chain connectivity for Desifn for test(DFT)
- Does NOT contain scan cell information
- Only Stores scan chanin connectivity (Q->SI).
- Scan cells inforamtion resides in the netlist(but scan cell connections are skipped).

