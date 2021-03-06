
# TeamA2_cheme485_final_project
**Topic: Problems at Cumene Production Facility: Unit 800** <br>

We are working on **Project 5**

# Planning Report 
**Assignments for the Planning Report:**

Planning reports are an informal check to make sure students are making adequate progress to finish their final reports. This is our attempt to reduce “busy work” of writing multiple reports. Planning reports will be graded on completion of each component. We will contant teams if we are worried the materials provided don’t reflect adequate progress. Planning reports must include:

**DUE: Wednesday, February 26th**

Planning reports must include:

**1.** A short abstract describing the process. - **Georges**
An overview of the process, what the targets are specified in the problem statement, identification of inputs and outputs, and general descriptions of the major sections of the process. This doesn’t need to be more than half a page in length.

----------------------------------------------------------------------------------------------------------------------------
The Cumene Production Facility buys **propylene** and **benzene** from a manufacturer to produce **cumene** and an undesired product, **p-diisopropyl benzene** (DIPB). The plant goal is to produce **90,000 metric tons per year of 99 wt% purity cumene**. The propylene and the benzene come liquid in the from a manufacturer, and we pump and heat them up to vaporize them since the reaction happens in the **vapor phase**. We will be using cooling water to cool off the product throught a heat exhanger since our reaction is **exothermic**, then the product will be sent into a flash drum. The flash drum will be splitting the product into a gas that will be used for **fuel** for a furnace , and the rest of the liquid will go into a first distillation column. In the first distillation column, we will be separating benzene from the rest of the product. The benzene will be **recycled** and mixed with the manufacturer benzene. The rest of the product from the first distillation column will be sent to a second distillation column. In the second distillation column, cumene will come out from the **distillate** end of the tower with a 99% purity and the waste DIPB will be leaving at the bottom and be used for **fuel** for a furnace. <br>
Recently, the company switched their supplier of propylene which is supposed to follow some speciifcations that applied to the previous supplier. Unfortunately, the production experienced an **8% drop in their production in cumene** due to the 8% increase in their reflux rate in order for them to maintain their 99% purity level requirement.

----------------------------------------------------------------------------------------------------------------------------
**2.** Hand-written block flow diagram of the process. - **Georges**

This can be hand-written and doesn’t need to be made in Visio. No stream tables or equipment tables need be present, but an overall mass balance should be provided.

----------------------------------------------------------------------------------------------------------------------------
![image](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Block%20Diagram.jpeg)

----------------------------------------------------------------------------------------------------------------------------
**3.** Initial data regarding the reaction kinetics necessary for simulations - **Emily**

These are the inputs necessary for a L2 reactor block in Aspen (reaction rates and activation energies). Most projects that are provided will include this reaction data, but if not, you may need to search the patent literature to find these.

----------------------------------------------------------------------------------------------------------------------------
The reactions involved in cumene production from benzene and propylene are:

 <img src = "cume_reactions.png" width=300>

The first reaction involves cumene production from propylene and benzene, while in the second the cumene and propylene react to form DIPB. Since cumene is our desired product, and DIPB is an environmental and health hazard, it is important to know the reaction kinetics, so that we may manipulate the environment to favor the cumene production reaction.

Each reaction has an independent rate, dependent on the molar concentration of each reactant and an individual reaction rate constant 'ka', where a denotes which reaction we are referring to. <br>

**In reaction 1, the cumene production reaction, the rate is:**

r<sub>1</sub> = k1 * C<sub>propylene</sub> * C<sub>benzene</sub>.  <br>

where <br>
k<sub>1</sub> = 3.5*10 <sup>4</sup>*e<sup>(-24.90/RT)</sup> <br>

<a href="https://www.codecogs.com/eqnedit.php?latex=r&space;=&space;k_1*C_{propylene}*C_{benzen}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?r&space;=&space;k_1*C_{propylene}*C_{benzene}" title="r = k_1*C_{propylene}*C_{benzene}" /></a>  

where  <br>
<a href="https://www.codecogs.com/eqnedit.php?latex=k_1&space;=&space;3.5*10^{-4}&space;exp(-24.90/RT)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?k_1&space;=&space;3.5*10^{-4}&space;exp(-24.90/RT)" title="k_1 = 3.5*10^{-4} exp(-24.90/RT)" /></a>

with <a href="https://www.codecogs.com/eqnedit.php?latex=E_a" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E_a" title="E_a" /></a>  being in kcal/mol.   <br>

In reaction 2, the DIPB production reaction, the rate is: <br>

r<sub>2</sub> = k2 * C<sub>propylene</sub> * C<sub>cumene</sub>.

where <br>

k<sub>2</sub> = 2.9*10<sup>6</sup>*e<sup>(-35.08 / RT)</sup> <br>

Which tells us the activation energy is 35.08 kcal/mol.

**In reaction 2, the p-diisopropyl benzene production reaction, the rate is:**

<a href="https://www.codecogs.com/eqnedit.php?latex=r&space;=&space;k_1*C_{propylene}*C_{cumene}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?r&space;=&space;k_1*C_{propylene}*C_{cumene}" title="r = k_1*C_{propylene}*C_{cumene}" /></a>  

where <br>

<a href="https://www.codecogs.com/eqnedit.php?latex=k_1&space;=&space;2.9*10^{4}&space;exp(-35.08/RT)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?k_1&space;=&space;2.9*10^{6}&space;exp(-35.08/RT)" title="k_1 = 2.9*10^{6} exp(-35.08/RT)" /></a>

with <a href="https://www.codecogs.com/eqnedit.php?latex=E_a" target="_blank"><img src="https://latex.codecogs.com/gif.latex?E_a" title="E_a" /></a>  being in kcal/mol. 

The differences in activation energies and the concentrations on which each reaction is dependent make it possible to favor reaction one by decreasing inlet energy (to ensure the activation energy for two is not reached) or supplying a high concentration of benzene, which is useless in reaction 2 but necessary in reaction 1.  

The units of the rates are mol/g cat-sec. These indicate that the reaction also depends on the weight of the phosphoric acid catalyst present in the reactor. This catalyst is supported on kieselguhr to maximize activity and surface area. For the shell and tube configuration used at the plant, the void fraction of catalyst is 0.5, the particle density is 1600 kg/m<sup>3</sup>, and the particle diameter is 3 mm. 
the heat transfer coefficient from packed bed to tube wall, 'h,' is 60 W/m<sup>2</sup> 

The units of the rates are mole/ g cat * sec. These indicate that the reaction also depends on the weight of the phosphoric acid catalyst present in the reactor. This catalyst is supported on kieselguhr to maximize activity and surface area. For the shell and tube configuration used at the plant, the void fraction of catalyst is 0.5, the particle density is 1600 kg/m^3, and the particle diameter is 3mm. The heat transfer coefficient from packed bed to tube wall, 'h,' is 60 W/m^2 * C. 

----------------------------------------------------------------------------------------------------------------------------
**4.** A suggested thermodynamics package and any extra information that needs to be gathered for the simulation - **Edwin**

Based on the information discussed in class on package selection, students should pick a package appropriate for their system and provide the rationale for doing so.

All information is taken **Don't Gamble with Physical Properties for Simulations**

----------------------------------------------------------------------------------------------------------------------------
Four factors that we must take into consideration when selecting thermodyanmic models/packages are: nature or properties, composition of mixture, the pressure and temperature range, and parameter availability.  
We would first go off the basis of the chemicals that are present in the process which include: Propylene, Benzene, Cumene, Propane, and p-diisopropyl benzene. Some notable operating conditions that these components will experience are temperatures 25-350 degrees celsius and pressures up to 31.25 bar. Although all compounds are hydrocarbons, they still do posses some degree of polarity, therefore not allowing for "All-Polar" packages suchs as Peng-Robinson, Redlich-Kwong or Chao-Seader.   Rather we assume we have polar components and that we have mixture containing no electrolytes. Additionally given that pressures we are working with exceed 10 bar, and that interaction parameters (extra information needed) were found readily through a quick google search, the reccomended package is:   

- **Redlich-Kwong-Soave with WS**  

----------------------------------------------------------------------------------------------------------------------------
**5.** An order of magnitude estimate of the design cost. - **Bri**

An order of magnitude cost estimate of the design cost. Order of magnitude estimates of capital costs can be performed if you have information on an existing plant that uses a similar process, but that won’t be the case for most projects. Instead, ignore capital costs and just examine the inputs (raw materials) and outputs (products) on an annual estimate to check that there is a potential for a profit before taking into account other costs.

----------------------------------------------------------------------------------------------------------------------------
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

The spreadsheet with detailed calculations for the order of magnitude cost estimation is provided 
[here](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/project_costing.xlsx) <br>

----------------------------------------------------------------------------------------------------------------------------
# PFD

**PFD and Stream Table**

![image](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-13%20at%2012.26.10%20AM.png)


**Equipment Summary** Emily <br>
![](equipment_summary_p1.png) 
![](equipment_summary_p2.png)


**Aspen PFD**

![image](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Aspen%20PFD.PNG) <br>
----------------------------------------------------------------------------------------------------------------------------

***Assignments for the Final Report*** <br>

**Letter of Transmission** <br> bri
Directions: This is a memorandum (if internal) or a letter (if external) to the appropriate person identifying the report. Teh report is actually an enclosure to this letter. Remember to refer to teh original memorandum or problem statement. In order to get the reader’s attention, writing several sentences summarizing the bottom line is essential. You should always sign or initial this memo or letter. This letter stands alone. It contains no figures or tables, and does not reference any figures or tables contained within the report.

**Title page** <br> bri
title, names, class name and date

**Abstract or Executive Summary** <br> em
Directions: Either an abstract or an executive summary should convey to the reader, in a rapid and concise manner, what you did, what you conclude, and what you recommend. This is for the reader who may not read any further or for the reader who is deciding whether or not to read any further. Summarize the bottom line; do not discuss computational details unless they are unique and applicable beyond the report at hand. In an executive summary (but not in an abstract), do not be afraid to use a few well chosen graphs, pie charts or histograms to emphasize your important points, but choose these wisely in order to keep the length of the executive summary down.

These instructions suggest that the contents of the abstract and letter of transmittal are similar. Since both sections are supposed to provide a summary of important conclusions, there will be significant repetition of content. The abstract usually contains more information than the letter of transmittal.

**Abstract (to be added to upon completion)**

Cumene is an important chemical intermediary, used to produce other chemicals such as phenol, acetone, acetophenone, and methyl styrene [1]. Our company's plant aims to produce its full capacity--90,000 metric tons yearly--of cumene with 99 weight % or greater purity with a vapor phase alkylation process catalysed by kieselguhr supported phosphoric acid.

The plant has been successful, but a recent change in our propylene suppliers heralded a number of issues, The change in plant operating conditions caused cumene production to drop by 8%, and reflux in T-801 had to be increased by 8% to maintain the requisite 99% purity. Fuel gas production increased by 78%, benzene recycle has increased and steam production in the reactor went down. Meanwhile, p-diisopropyl benzene (p-DIPD), the product of a side reaction involving propylene and cumene, was produced at 20% lower rates. A warm spell caused damage to P-802. The plant has numerous competitors, so our team’s goal was to fix these issues and lower production costs.

We modeled the ideal process and the issues on ASPEN, then used single variable optimization of reflux ratio, catalyst density, catalyst weight, reactor temperature, and reactor pressure to establish a baseline of effective variable changes. The single variable optimization did not produce the requisite 99% purity of cumene.  A subsequent multivariable optimization successfully produced 92.269 kmol/hr of cumene at 99.05% purity while incresing the rate of p-DIPD production and decreasing fuel gas production.

In the idealized situation, the pressure into the reactor increased to 50 bar, and the temperature dropped to 300 C. The high pressure increases the frequency of gas  molecule collisions, and therefore the rate of the vapor-phase reaction, resulting in greater cumene production. Since temperature had very little effect on comene production, it was decreased for optimal energy usage. The reflux ratios of T-801 and T-802 were decreased  to .3 and .6, respectively. Decreasing T-801’s reflux ratio results in less cumene being released into the recycle stream. At the old reflux ratio, T-802 produced very high purity cumene at slightly lower rates. Dropping the reflux ratio brings purity down to 99% and raises distillate rate to 92.269 kmol/hr.

**TALK A BIT ABOUT COSTS** 

**Table of Contents** <br> em (after the fact) <br>
This is only necessary for longer reports. At the top of the page, the proper title is “Contents,” not “Table of Contents.” Regardless of whether you include a table of contents, all pages of your report should be numbered, preferably at the top right corner or top center (the latter permits easy two-sided copying). Number, indent, or otherwise indicate sections, subsections, etc.

**Contents**<br>
0.0 Letter of Transmittal <br>
0.1 Title Page <br>
0.2 Abstract <br>
1.0 Introduction <br>
2.0 Results <br>
    2.1 Process Flow Diagram <br>
    2.2 Stream Tables <br>
    2.3 Manufacturing Cost <br>
    2.4 Investment Summary <br>
    2.5 Equipment Summary <br>
3.0 Discussion <br>
4.0 Conclusion  <br>
5.0 Reccomendations <br>
6.0 References <br>

**Introduction** <br> edwin <br>
This is for the reader who continues past the abstract. The introduction is a one or two paragraph summary of what was assigned, what was done, and, (very briefly) how it was done. A summary of the constraints on the problem is appropriate, as well as some perspective on the specific problem in the context of the larger business picture. There should be no results or conclusions in the Introduction section.



**Results** <br>
The following are essential components of a results section: 

*Labeled and dated process flow diagram (PFD). Georges <br>
Stream flow tables. These must include temperature, pressure, phase, total mass flow rate, total molar flow rate, and component molar flow rates for each numbered stream. Georges<br>
Manufacturing cost summary. Yearly revenue and expense (income from product sales, expenses for raw materials, utilities [itemized], equipment costs if calculated as an annual cost, personnel, etc.) must be included. Bri **DONE** <br>
Investment summary. The cost to build and install plant now (if appropriate to goals of the problem). This should be itemized by piece of equipment. Bri **DONE** <br>
Equipment summary. A listing of equipment to be purchased and installed, with specifications required. This could be combined with 4. if not too long.* <br> Bri  **DONE** ***Pls check it out tho*** <br>

**Capital Costs** **This is all I plan to do so check it over - Bri ** <br>

The Direct Capital Costs (CD) is $113.1 million/year, with raw materials consisting of over 90% of the total. The full estimated breakdown of the Direct Capital Costs is shown in Table #. Estimation was conducted according to Table 8.2 in Turton. Further breakdowns of raw materials and utilities are in Tables 2 and 4 below. The prices for materials are from ICIS and utility prices from Turton and are assumed to be 2012 values.  <br>

*Table 1. Cost factors for capital costs.* <br>
![breakdown](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-15%20at%2012.12.24%20PM.png) <br> 

The table below include pricing for all streams entering or leaving the process as a whole. The first three are reactant streams containing propylene/propane and benzene which equate to raw material costs. This accounts for the majority of direct capital costs. The following two rows are products streams which are revenue producing. Revenue per annum for the cumene production facility is $155 million which demonstrates that the process is both feasible and profitable. <br>

*Table 2. Annual material costs and prices of reactants and products. Propylene, propane, and benzene are costs, and cumene is a profit.* <br>
![crm](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-15%20at%2012.12.34%20PM.png) <br> 

Although raw material costs and revenue of the overall process can be approximated using input and product streams alone, the fuel gas product stream acts as fuel for the furnace, thus cost savings are realized by analyzing the production of fuel gas. The full breakdown of each fuel component and their heat of combustion is provided in Table 3. The price per kilogram was calculated using the heats of combustion multiplied by a fuel credit of $2.50/GJ of each component. The heats of combustion and molecular weights are sourced from NIST Webbook. Therefore, the last column in Table 3 is subtracted from the utility costs for the furnace on-site since that amount of fuel would not need to be outsourced to run that equipment at the facility. <br>

*Table 3. Annual fuel recovery costs and heats of combustion for materials. Products in streams 9 and 14 are recycled as fuel for the cumene production facility.*
![fuel](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-15%20at%2012.12.42%20PM.png) <br> 

Table 4 below depicts utility costs for relevant equipment. H-801 uses natural gas, but this partially accounted for using fuel gas credit from distillate from T-801 and impurities from the flash unit V-802 (refer to Table 3). The reboilers all use either medium- or high-pressure steam while pumps require electricity. Coolers require cooling water. All utility prices are from Turton and are assumed to be 2012 values. 

*Table 4. Annual utility costs for selected equipment.* <br>
![utilities](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-15%20at%2012.12.50%20PM.png) <br> 

The total manufacturing costs without depreciation, COMd can be estimated by adding three categories together: CRM, CUT, and COL.  <br>

COM<sub>d</sub> = 0.18*FCI<sub>L</sub> + 2.76(C<sub>OL</sub> + 1.23(C<sub>UT</sub> + C<sub>WT</sub> + C<sub>RM</sub>) <br>

Solving for COM<sub>d</sub> using the information in Table 1, a value of $138 million is obtained. This approximation indicates that direct capital costs account for over 80% of the manufacturing costs. The COM<sub>d</sub> does not take the estimating factors from Table 1 into account, but raw materials and utilities account for a large portion of total costs, thus the COM<sub>d</sub> is generally insensitive to these estimating factors.  <br>

**Fixed Capital Investment**

The Fixed Capital Investment (FCI<sub>L</sub>) for the project is expected to be $30 million. This was calculated by multiplying the sum of the Total Module Cost (C<sub>TM</sub>) and half the Bare Module Cost (C<sub>BM</sub>) by the Lang Factor of a fluid processing plant, F<sub>Lang</sub> = 4.74. The Bare Module Cost is calculated in Table 5 below, which shows the equipment in the plant, the purchase cost, and C<sub>BM</sub>. CAPCOST was used to price equipment, using the CEPCI for 2010, which is 551. <br>

*Table 5. Purchase and bare module cost for all major equipment.* <br>
![fci](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/Screen%20Shot%202020-03-15%20at%2012.13.34%20PM.png) <br> 
The total C<sub>BM</sub> is just below $3.8 million which yields a C<sub>TM</sub> of approximately $4.4 million. This gives an FCI<sub>L</sub> of $ 30 million. <br>

The CAPCOST sheet used to make these estimations is provided [here](https://github.com/Antonedw/teamA2_cheme485_final_project/blob/master/project_CAPCOST.xlsm). <br>
**still need to CAPCOST s the addition of new equipment after modifications are made 

**Reactor config**
Cumene creation in our system can be improved by changing reactor conditions. To optimize these conditions we performed a two variable optimization on the temperature and pressure inlets to the reactor. The spreadsheet with the combined ASPEN and CAPCOST information can be found [here](Reactor_optimiz.xlsx).  <br>
Conversion is a useful way to measure the efficiency of a reaction at creating the desired product. So, we created an analysis that compared temperature, pressure, and conversion of cumene. We found: <br>
![](r_proof_1.png) <br>
As you can see, conversion is lowest at the plant's current condition, where the change in propylene providers has introduced an impurity but no change has been made to the reaction. As expected, pressure had little impact on conversion; pressure changes the frequency of reactions by changing reactant density, but it does not affect activation energy or how these reactions occur. Interestingly, both increasing and decreasing temperatures in the reaction have similar effects on the conversion.

The quantity of cumene product leaving the reactor, and the amount leaving the process to be sold (stream 13 on the PFD (**See PFD**)) are another measure of plant efficiency. So, we measured both as pressure and temperature in the reactor changed: <br>
![](r_proof_2.png) <br>
![](r_proof_3.png) <br>
Both follow the same trend. As you can see, lower temperatures correspond to greater cumene outlets, both in the reactor outlet and in the process’ outlet stream. This is unexpected, as higher temperatures generally increase rates of reaction. However examining stream 14, the outlet for p-diisopropyl benzene, shows higher temperatures correspond to greater mass flow rates in stream 14 (**See PFD**). <br>
![](r_proof_4.png) <br>
Since p-diisopropyl benzene is the product of a side reaction, this implies that higher temperatures favor the side reaction. <br>

The cumene product can only be sold if its purity is 99% or greater. So, we determined the purity of stream 13 (**See PFD**): <br>
![](r_proof_5.png)<br>
As you can see, the purity is only sufficiently high when T drops to 300C. <br>
At 300C, Pressure impacts outlet: at P = 45 bar the rate of cumene product production is ~0.35 kg/hr greater than it is at P = 30 bar. However, this change is relatively small, and the process has multiple products. <br> 
![](r_proof_6.png)
These results indicate that optimization will depend on cost. Since the equipment has already been purchased, the cost depends on utility pricing, inlet chemical purchase price, and product sales. Examining the case where only reactor utility costs impact results yields: <br>
![](r_proof_7.png)<br>
However, many of these changes occur in the heater, so we performed another analysis that included heater utility and found: <br>
![](r_proof_8.png)<br>

So, the modified equipment is:<br>
![](Equip_sum1.png)<br>
![](Equip_sum2.png)<br>

New reactor putrchases will need to account for high pressures, in the case where heater utility is ignored, meaning that they will need thicker walls.


**Discussion** <br> everyone
=======


**Discussion** <br>

Now you go into more detail. This section is for the reader who still wants more information and is willing to read still further. Here you discuss the reasons for making choices and the reasons for discarding alternatives. This is where you discuss any optimization that was done. You might also discuss non routine or unique computational aspects

Increasing impurity in the reactant stream inhibits the reaction by diminishing the number of collisions between reactants. Ameliorating this necessitates changing reactor conditions.<br>

We decided to vary temperature and pressure into the reaction by examining reaction kinetics. In gas phase reactions, temperature changes affect the amount of energy in molecule movements, and pressure changes affect the density of the reactants, and therefore the frequency of their collisions.  <br>

To do this, we modeled the system using Aspen, and calculated prices with CAPCOST. The condition of the stream flowing into the reactor was decided at the heater. To compare the cost of one variation over the next, we used the utility costs and the gain from cumene production. The utility costs examined were first of the reactor system only, and then included the heater utility.  <br>

We found that the reactor produced high masses of high purity  cumene product when temperatures were decreased to 300C and pressures were increased to 45-50 bar. <br>
Decreasing the temperatures drops the average rate of both reactions. More specifically, it increases the rate of reaction 1, which creates the cumene product, and decreases the rate of the side reaction. This is because the activation energy of the side reaction is higher than that of reaction 1. Decreasing temperatures mean the molecules have less energy, causing the process to favor the first reaction, resulting in greater amounts of cumene product. Since the reaction is in the vapor phase, increasing pressure increases the density of the reactants, causing more frequent collisions and therefore faster reactions.<br>


**Conclusions** <br> em, edwin
Nothing new is presented in this section. You should reiterate your important conclusions, which may have already been stated in the abstract, the executive summary, and/or the letter of transmittal. Usually these will involve dollars and process modifications. Be concise and clear; avoid lengthy paragraphs. Once again, remember the bottom line!

**Recommendations** <br> Georges
This section includes recommendations for further action and/or further study. If there are few conclusions and recommendations, these two sections can be combined. Avoid recommendations that are “pie in the sky,” like finding a better catalyst.

**References** <br> georges
1 http://www.npi.gov.au/resource/cumene-1-methylethylbenzene
2 https://www.chemicalbook.com/Price/CUMENE.htm

