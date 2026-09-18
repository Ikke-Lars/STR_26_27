# STR_26_27
Group 27, Structure

### Identified issues:
#### 1. Team 26-09 report:
Columns have been evaluated wrongly, since it is claimed that their carrying capacity have been surpassed (and the building still stands).
 - a possible solution for this problem have been tackled by already completed tools (2520: IFC Column axial capacity analysis). But that is without any external loads implemented onto the column.

#### 2. Team 26-08 Model/Tool:
The model (& tools) are missing information for describing the support conditions of general structural elements. I.e the relationship between multiple structural elements cannot be described.
 - A solution for this could be for example that a specific point of a beam has described the support conditions and how great of a surface the conditions cover. Furthermore the relationship between two structural elements could be described via the same points. However this could seem like an IFC issue and not so much as a possible tool.


#### 3. Team 26-08-STR Model:
For every element of Beam and Column there is one type as a parent for that element. That means that there are X number of beams and X number of BeamTypes. This is because that for every element type there is a duplicate for that number of elements using that specific type, fx. IfcBeamType/S202 has multiple IfcBeamType/S202.016, IfcBeamType/S202.017, IfcBeamType/S202.018 and so on. It seems that its a bug from bonsai, but still needs to be assessed.
 - Solution: A cleaning tool, that compares the property sets of duplicate types. If they are similar the tool could join them under the parent type and delete the duplicates.
