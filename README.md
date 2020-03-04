
# TeamA2_cheme485_final_project
**Topic: Problems at Cumene Production Facility: Unit 800** <br>

We are working on **Project 5**

**Assignments for the Planning Report:**

Planning reports are an informal check to make sure students are making adequate progress to finish their final reports. This is our attempt to reduce “busy work” of writing multiple reports. Planning reports will be graded on completion of each component. We will contant teams if we are worried the materials provided don’t reflect adequate progress. Planning reports must include:

**DUE: Wednesday, February 26th**

Planning reports must include:

**1.** A short abstract describing the process. - **Georges**
An overview of the process, what the targets are specified in the problem statement, identification of inputs and outputs, and general descriptions of the major sections of the process. This doesn’t need to be more than half a page in length.

------------------------------------------------------------------------------------------------------------------------------
The Cumene Production Facility buys **propylene** and **benzene** from a manufacturer to produce **cumene** and an undesired product, **p-diisopropyl benzene** (DIPB). The plant goal is to produce **90,000 metric tons per year of 99 wt% purity cumene**. The propylene and the benzene come liquid in the from a manufacturer, and we pump and heat them up to vaporize them since the reaction happens in the **vapor phase**. We will be using cooling water to cool off the product throught a heat exhanger since our reaction is **exothermic**, then the product will be sent into a flash drum. The flash drum will be splitting the product into a gas that will be used for **fuel** for a furnace , and the rest of the liquid will go into a first distillation column. In the first distillation column, we will be separating benzene from the rest of the product. The benzene will be **recycled** and mixed with the manufacturer benzene. The rest of the product from the first distillation column will be sent to a second distillation column. In the second distillation column, cumene will come out from the **distillate** end of the tower with a 99% purity and the waste DIPB will be leaving at the bottom and be used for **fuel** for a furnace. 

**2.** Hand-written block flow diagram of the process. - **Georges**

This can be hand-written and doesn’t need to be made in Visio. No stream tables or equipment tables need be present, but an overall mass balance should be provided.

![image](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Block%20Diagram.jpeg)

**3.** Initial data regarding the reaction kinetics necessary for simulations - **Emily**

These are the inputs necessary for a L2 reactor block in Aspen (reaction rates and activation energies). Most projects that are provided will include this reaction data, but if not, you may need to search the patent literature to find these.

The reactions involved in cumene production from benzene and propylene are:

![](cume_reactions.png)

The first reaction involves cumene production from propylene and benzene, while in the second the cumene and propylene react to form p-diisopropyl benzene. Since cumene is our desired product, and p-diisopropyl benzene is an environmental and health hazard, it is important to know the reaction kinetics, so that we may manipulate the environment to favor the cumene production reaction.

Each reaction has an independent rate, dependent on the molar concentration of each reactant and an individual reaction rate constant 'ka', where a denotes which reaction we are referring to.

In reaction 1, the cumene production reaction, the rate is: 

rate = k1 * concentration of propylene * concentration of benzene.

where

k1 = 3.5 * 10^4 * exp(-24.90 / RT)

Which tells us the activation energy is 24.90 kcal/mol.


In reaction 2, the p-diisopropyl benzene production reaction, the rate is: 

rate = k2 * concentration of propylene * concentration of cumene.

where

k1 = 2.9 * 10^6 * exp(-35.08 / RT)

Which tells us the activation energy is 35.08 kcal/mol.


The differences in activation energies and the concentrations on which each reaction is dependent make it possible to favor reaction one by decreasing inlet energy (to ensure the activation energy for two is not reached) or supplying a high concentration of benzene, which is useless in reaction 2 but necessary in reaction 1.


The units of the rates are mole/ g cat * sec. These indicate that the reaction also depends on the weight of the phosphoric acid catalyst present in the reactor. This catalyst is supported on kieselguhr to maximize activity and surface area. For the shell and tube configuration used at the plant, the void fraction of catalyst is 0.5, the particle density is 1600 kg/m^3, and the particle diameter is 3mm. 
the heat transfer coefficient from packed bed to tube wall, 'h,' is 60 W/m^2 * C

**4.** A suggested thermodynamics package and any extra information that needs to be gathered for the simulation - **Edwin**

Based on the information discussed in class on package selection, students should pick a package appropriate for their system and provide the rationale for doing so.

All information is taken **Don't Gamble with Physical Properties for Simulations**

Four factors that we must take into consideration when selecting thermodyanmic models/packages are: nature or properties, composition of mixture, the pressure and temperature range, and parameter availability.  

We would first go off the basis of the chemicals that are present in the process which include: Propylene, Benzene, Cumene, Propane, and p-diisopropyl benzene. Some notable operating conditions that these components will experience are temperatures 25-350 degrees celsius and pressures up to 31.25 bar. Although all compounds are hydrocarbons, they still do posses some degree of polarity, therefore not allowing for "All-Polar" packages suchs as Peng-Robinson, Redlich-Kwong or Chao-Seader.   Rather we assume we have polar components and that we have mixture containing no electrolytes. Additionally given that pressures we are working with exceed 10 bar, and that interaction parameters (extra information needed) were found readily through a quick google search, the reccomended packages are:   
- Schwartentruber-Renon,  
- Peng-Robinson or Redlich-Kwong-Soave with WS,  
- Peng-Robinson or Redlich-Kwong-Soave with MHV2  

**5.** An order of magnitude estimate of the design cost. - **Bri**

An order of magnitude cost estimate of the design cost. Order of magnitude estimates of capital costs can be performed if you have information on an existing plant that uses a similar process, but that won’t be the case for most projects. Instead, ignore capital costs and just examine the inputs (raw materials) and outputs (products) on an annual estimate to check that there is a potential for a profit before taking into account other costs.

The cost of inputs and outputs were calcualted with input benzene and propylene (Streams 1 and 2) and output fuel, high-purity cumeme, and waste DIPB (Streams 9, 13, and 14). <br>
From Table 8.4, the cost of raw materials benzene and propylene were estimated. From Ex. 14.1, the heats of combustion for propane, cumene, and DIPB and average fuel credit were used to quantify the net revenue for sale of fuel in the waste streams. <br> 

The individual pricing of raw materials and the standard heats of combustion for fuel products are summarized in the tables below:  <br>

| Raw materials | Cost  | Unit |
| --------------|-------| ---- |
| benzene 	    | $0.92 | $/kg |
| propylene 	  | $1.44 | $/kg |

| Fuel products  | Heat of Combustion | Unit    |
| -------------- | ------------------ | ------- |
| propane        |	   2.22	          | GJ/kmol |
| cumene 	       |     5.00 	        | GJ/kmol |
| DIPB           |     6.82 	        | GJ/kmol |

Assuming 8000 operating hours per year and neglecting the small fraction of propane contained in the propylene input stream, the annual net profit for this process is approximately $127,110,932.07. <br> 

The spreadsheet with detailed calculations for the order of magnitude cost estimation is provided [here](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/project_costing.xlsx) <br>

**Equipment Summary** <br>
P-803: The pump is a 75% efficient centrifugal pump with a driver rated at 2.4 kW.
P-804: The pump is a 75% efficient centrifugal pump with a driver rated at 1.0 kW.
P-805: The pump is a 75% efficient centrifugal pump with a driver rated at 3.3 kW.

E-801: uses HPS (high pressure steam) in the shell with Q= 12,800 MJ/hr. A = 20.8m^2 in two zones, Desubcooling zone has A=13.5m^2, U=600W/m^2* C, hi = 667 W/m^3 * C, Vaporizing zone: A= 7.3 m^2, U = 1500 W/m^2 C with equal resistance on both sides


E-802: condensor for a flash unit, with the process stream in the shell, in a 1-2 configuration. Q=16,400 MJ/hr, A=533m^2
E-803: total condensor for a T-801, with the condensing fluid in the shell. 
 A=151m^2, U = 450 W/m^2C and all resistance on the water side.
E-804: reboiler T-801. 
 A=405m^2, U = 750 W/m^2C approx equal resistances.
E-805: total condensor for T-802, with the condensing fluid in the shell. 
 A=24m^2, U = 750 W/m^2C anpprox equal resistances.
E-806: reboiler T-802. 
 A=64m^2, U = 750 W/m^2C approx equal resistancese.


Fired heater H-801: Q= 6380 MJ/h of heat added to fluid, capacity 10,000MJ/hr, 70% efficiency

Reactor: R-801: A shell and tube packed bed reactor with keiselguhr-supported phosphoric acid catalyst. Boiler feed water in shell produces HPS, reactor volume is 6.5 m^3, exchange area is 342 m^2, 234 tubes each 6m long



 V-801: This is the benzene feed drum: in this vessel, the Benzene feed and recycle stream are combined. 
 
P-801A/B: This benzene feed pump raises the pressure of the combined benzene feed and recycle stream from 1.01 bar to 31.5 bar, and the temperature from 41 to 44 degrees C. P-801 is a 75% efficient centrifugal  with a driver rated at 21.9 kW.

P-802A/B: The propylene feed pump raises pressure of the the propylene feed in stream 2 from 11.66 bar to 31.5 bar. The pump is a 75% efficient centrifugal pump with a driver rated at 6.8 kW.
<br>
<br>
-------------------------------------------------------------------------------------------------------------------------------

***Assignments for the Final Report*** <br>

**Letter of Transmission** <br>
Directions: This is a memorandum (if internal) or a letter (if external) to the appropriate person identifying the report. Teh report is actually an enclosure to this letter. Remember to refer to teh original memorandum or problem statement. In order to get the reader’s attention, writing several sentences summarizing the bottom line is essential. You should always sign or initial this memo or letter. This letter stands alone. It contains no figures or tables, and does not reference any figures or tables contained within the report.

**Title page** <br>
title, names, class name and date

**Abstract or Executive Summary** <br>
Directions: Either an abstract or an executive summary should convey to the reader, in a rapid and concise manner, what you did, what you conclude, and what you recommend. This is for the reader who may not read any further or for the reader who is deciding whether or not to read any further. Summarize the bottom line; do not discuss computational details unless they are unique and applicable beyond the report at hand. In an executive summary (but not in an abstract), do not be afraid to use a few well chosen graphs, pie charts or histograms to emphasize your important points, but choose these wisely in order to keep the length of the executive summary down.

These instructions suggest that the contents of the abstract and letter of transmittal are similar. Since both sections are supposed to provide a summary of important conclusions, there will be significant repetition of content. The abstract usually contains more information than the letter of transmittal.

**Table of Contents** <br>
This is only necessary for longer reports. At the top of the page, the proper title is “Contents,” not “Table of Contents.” Regardless of whether you include a table of contents, all pages of your report should be numbered, preferably at the top right corner or top center (the latter permits easy two-sided copying). Number, indent, or otherwise indicate sections, subsections, etc.

**Introduction** <br>
This is for the reader who continues past the abstract. The introduction is a one or two paragraph summary of what was assigned, what was done, and, (very briefly) how it was done. A summary of the constraints on the problem is appropriate, as well as some perspective on the specific problem in the context of the larger business picture. There should be no results or conclusions in the Introduction section.

**Results** <br>
The following are essential components of a results section:

Labeled and dated process flow diagram (PFD).
Stream flow tables. These must include temperature, pressure, phase, total mass flow rate, total molar flow rate, and component molar flow rates for each numbered stream.
Manufacturing cost summary. Yearly revenue and expense (income from product sales, expenses for raw materials, utilities [itemized], equipment costs if calculated as an annual cost, personnel, etc.) must be included.
Investment summary. The cost to build and install plant now (if appropriate to goals of the problem). This should be itemized by piece of equipment.
Equipment summary. A listing of equipment to be purchased and installed, with specifications required. This could be combined with 4. if not too long.

**Discussion** <br>
Now you go into more detail. This section is for the reader who still wants more information and is willing to read still further. Here you discuss the reasons for making choices and the reasons for discarding alternatives. This is where you discuss any optimization that was done. You might also discuss non routine or unique computational aspects

**Conclusions** <br>
Nothing new is presented in this section. You should reiterate your important conclusions, which may have already been stated in the abstract, the executive summary, and/or the letter of transmittal. Usually these will involve dollars and process modifications. Be concise and clear; avoid lengthy paragraphs. Once again, remember the bottom line!

**Recommendations** <br>
This section includes recommendations for further action and/or further study. If there are few conclusions and recommendations, these two sections can be combined. Avoid recommendations that are “pie in the sky,” like finding a better catalyst.

**References** <br>
