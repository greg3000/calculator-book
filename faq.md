# Frequently Asked Questions

## Agriculture & waste

In the sheet, there are only dairy cows while in Vietnam (2010) we have about 130,000 dairy cow heads and about 5,000,000 non-dairy cow heads and 2,913,000 buffalos. Do you think we are missing some GHG from this cattle?

~    The goal of the UK version was to include the main categories of farm animals without getting into too much detail. If you think the emissions factor is very different for dairy, non-dairy and buffalo, then you might want to have a category for each one.  What we’d recommend though is to have one category in the Calculator for all cattle/buffalo (dairy, non-diary, buffalo), e.g. add up the totals you mentioned in your email (130000+500000+2913000= 8043000) and multiply these by a single emissions factor. This will save you work, and will make the model easier to manage.

For the first generation energy crops I count: sugarcane, soybean, peanut, coconut and sunflower (but no data for sunflower)  Same for second generation energy crop I count: rice straw, maize straw, peanut and soybean residue, sugarcane residue and cassava root, (there is jatropha but no data about it)

~    Your work on first and second generation biocrops sounds correct. For sunflower and jatropha even if there is no data for Vietnam at the moment, you might still want to include scenarios out to 2050 for what could be achieved with these crops.  When you have your workshops, some questions you might want to ask your experts would be: Will sunflower/jatropha be an option in Vietnam in the next 30 years? Are there any other 1st or second generation biofuels that should be considered in the Vietnam Calculator?

The agricultural practices, such as N (nitrogen) fertilizer use, have large impact on emission. How is the N fertilizer use taken into account? (If it is the soil management practice what does the annual change mean (%pa): What is changing at that rate?)

~    We capture the total emissions per km2 of land farmed in the “soil management” assumptions in sheet VI.a. We do not look at choices on specific fertilizer.  The change in emissions from soil management reflects changes in through continued improvement in nutrient management practices on farms (declines are limited by an increase in bioenergy crop land in the scenarios where this occurs).

Regarding land use change, how do the different uses (1st gen, 2nd gen.etc.) of grasslands and arable lands affect emissions? (VI.a sheet)

~    Farming and biofuels production require energy and this has associated emissions. Crop land and grassland have different emissions factors but emissions are not differentiated by crop type.

With considering the forest area – is it only because of bioenergy uses or also adding the total CO2 absorption capacity of plants?

~    We include the CO2 sequestered by forests. The model covers all emissions and should reflect aggregate net emissions data.

At waste management what does the abbreviation CDW stand for? (VI.b sheet)

~    Construction and demolition waste

In waste management (sheet name) what do the following abbreviations stand for?

~    RC to go through sheet and find all abbreviations e.g. odt

## All sectors

Is there any easy way to identify the location of external references in the Excel file so that we can remove them?

~    Yes, you could try this macro: https://gist.github.com/tamc/dc15127a0b7475689e4e.  We also have a detailed set of instructions for merging sheets into the master spreadsheet, and identifying external references in named ranges or cells. (RC to add link)

Could you please explain me in more detail which is the use of the subtotals in the years sheets?. Is it important to the calculations of the energy balance or is it only to make summary of the calculations?

~    On your subtotals question, our 2050 book has an explanation which should be helpful for you:  http://book.2050.org.uk/calculator-book/appendix-1-the-excel-model-structure.html#year-sheets     There is also another part we haven’t yet added to the book, but you might find useful:    Communication between sectors  There are a number of places where an apparently ad hoc energy flow calculation is performed within the annual balance sheets rather than in a sectoral worksheet. In particular, you will notice that subtotals are calculated for certain fuel types and used by the heat supply (XVII.a), power generation (II.a, I.b, I.a), electricity distribution (VII.b), and biomass (V.a and V.b) sectors, a subtotal is computed. This subtotal is the total energy flow, of a particular fuel type, from a subset of the sectors. (There is a similar calculation done for XVI.b, balancing imports, which really should have been done in its own sectoral worksheet).  What is going on turns out to be straightforward, although it certainly doesn't appear so at first glance. The job of certain sectors is to supply (or demand) an amount of energy that is not fixed by the assumptions, but depends upon what is demanded by the rest of the model. For example, electricity from gas generation is produced in whatever quantity is required to meet the total demand for electricity. So somehow the amount of electricity demanded needs to be passed to that sector. The subtotal adds up all the flows except those from one particular sector.

If we keep the same levers, how much can we change numbers from the UK version?

~    It's up to your team to make a judgment about your trajectories and fixed assumptions, based on your country data and stakeholder expertise. But a few things to consider are:  -the UK's infrastructure (e.g. housing/transport) and trends may be very different to your country. Consider the differences currently, and think about what changes are most likely to happen in your country.  - avoid extreme figures which seem unlikely to be average for the whole country - e.g. bus occupancies of 45 may be very ambitious, given that there are times of data and parts of the country when vehicles will not be full to capacity  - be careful about extrapolating trends into the future: a small percentage increase now could make a very big difference in 2045, especially if you are assuming exponential growth. Make sure that you sense-check all your numbers, and discuss 2050 values with stakeholders.

Why is such a complicated formula used. For example, in the UK's nuclear sheet II.a, row 28 has the following formula:  =(INDEX(G$24:G$27,ROUNDDOWN($E$7,0))*(1-MOD($E$7,1)))+(INDEX(G$24:G$27,ROUNDUP($E$7,0))*MOD($E$7,1))

~    This formula allows people to enter any fractional levels between 1 and 4, so that people can choose any level of ambition that they want.  The way it does this is by interpolating between the two levels. So for example if someone selects level 2.25, the calculation will take:  the value for level 2 + 1/4 of the difference between level 2 and level 3.

Sometimes we don't have any accurate predictions about the future - when is it OK to just assume that current values will continue?

~    This is a really important question. For some assumptions, the difference they make is so negligible they will have no visible impact on any results. In this case, where there is no historic data available, it is reasonable to assume that today's values will continue into the future.  However for data that is likely to change results significantly, it might be better to:  -assume some level of sensible growth rather than none at all (this might involve projecting historical values into the future). You will need to decide whether this growth will be a straight line, or a curve  -you can also add this as an uncertain assumption where more stakeholder input is needed and open it out to stakeholder discussions.    In order to identify which assumptions are most critical to the final results, you could do sensitivity testing - this means just testing the most extreme values this assumption could take (for example, doubling and halving current values), and then seeing what effect this has on the end result. If it makes very little difference, then this assumption is less worth spending time on.

When should we use documentation/footnotes and when not?  For example, we used other models to forecast the change in different Mexican cities. Should we include all of that detail in the main spreadsheet?

~    The main reasons for using documentation are:  Simplicity - it makes the spreadsheet much easier to use and to follow (especially when you use clear labels, and put more detailed notes into footnotes so that it doesn't break up the page too much)  Transparency - any colleagues and stakeholders can immediately see your sources, recreate data or substitute their preferred data  To avoid confusion -for example, if someone might expect a calculation to use rural population, but you have decided to total population, you should explain the reasoning behind your decision. Without this, someone might misunderstand the numbers, or it might be picked up as an error in future, when actually this is what you intended to do  To enable stakeholders/future developers of the spreadsheet to track down the data that you used, or recreate the reasoning you have used.    So in this example, we would recommend using footnotes which describe your methodology in a sentence or two. Then (if possible) we'd suggest including a link to any separate spreadsheets you have used, so that people can see more detail. But this isn't essential, particularly in a first launch, as it can easily be added later.

Initially we didn't quite feel to change the spreadsheet so much. At first we were quite cautious, didn’t want to risk breaking some process  Now we’re more confident, but could you give us any advice about where it's fine to change the spreadsheet, and where we should be more careful?

~    We recommend keeping the same overall structure as the UK calculator, but there is plenty of flexibility to make changes yourself once you have familiarised yourself with the way the calcualtor works. The parts we would advise you not to change (because of the webtool) are: the Control sheet layout, the intermediate output sheet, the key named ranges (everything to do with units, preferences, inputs and outputs).  We recommend using a colour-coding, so that your whole team uses the same conventions to mark areas of the spreadsheet:  - you may want to make that have been changed, are about to be changed  - you will want to indicate parts of the spreadseheet which are still using UK figuresx  - you might also want to use a consistent colour to mark numbers which have been changed as a rough estimate, but that you are still planning to go back to and improve

## Balancing

Did you design the year sheets according to the UK energy balance? Would we want to keep the same order of sectors and energy sources, or should we customize the spreadsheet according to Colombia’s energy balance.

~    We arranged the UK version according to the way that our Calculator is structured, and to some extent, based on the way that our statistics are recorded. If you want to make changes to the year sheets for Colombia that is fine – particularly if it would make it more credible for experts in Colombia. The main rules you should follow is that you should account for all of the vectors in your individual sector/technology sheets, and you should be careful to make sure you don’t double-count units of energy.  It’s worth looking in detail at one of the UK year sheets if you have not done so already as there are some aspects of them that are based on how our energy system works. The link below explains how the year sheets work, or we’d be happy to do that with you if that sounds useful: http://book.2050.org.uk/calculator-book/appendix-1-the-excel-model-structure.html#year-sheets

In the Control sheet, the Energy Demand plot contain a "Dummy" series, whose purpose (at least visually) seems to be balancing with supply, even when demand is actually lower. Where is this Dummy defined and controlled?

~    The dummy is defined in row 20 of the intermediate output sheet. The series isn’t visible on the chart as it’s transparent – so isn’t really important. As you mention, this series shows the difference between total demand and total primary supply (more on this below).

We were given to understand that the Calculator automatically balances demand and supply, but this does not seem the case from the plots (for instance, the standard scenario gives a much higher output supply than demand, with the Dummy series apparently compensating). Is balance only considered for the emissions? How are the various energy sources affected?

~    The key thing here is that the demand plot shows final consumption and the supply plot shows primary supply.   This difference between these two is explained by losses (conversion, transmission, etc).

I have the problem of understanding functions in sheet I.a, table "Electricity required". Could you pls. explain, preferably with example similar to those you used during your lecture.

~    This sector forms part of the balancing mechanism within the calculator, which ensures that any shortfall in electricity supply is met by fossil fuels sector. Row 15 returns the total final electricity demand across all of the demand sectors. Row 16 calculates how much low carbon electricity is being generated by your pathway. Further down the sheet the difference between these two values is calculated, which is equivalent to the shortfall in electricity supply under the chosen pathway. This determines the amount of electricity that needs to be generated within sector 1.a, i.e. using fossil fuels.    The formulae used here are a little bit complex, e.g. from =I.a!F15: =INDEX(INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Matrix"), MATCH("Subtotal."&$A$2, INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Modules"), 0), MATCH([Vector], INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Vectors"), 0))  This is essentially an index function, which allows you to return a value from an array based on a row and column that you specify. Here the row and columns references are specified using match functions, which effectively look through the row and column labels and return the position of the thing (i.e. vector/sector) that you are looking for. I’ve broken this down into its components below and tried to give an explanation of what is happening:  =INDEX(INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Matrix") – this part of the formula specifies the array, by combining the corresponding header from the 1.a.inputs table (here 2007) with the text “!Year.Matrix” to look at the named range of cells called Year.Matrix on the 2007 year sheet. Referring to the name manager (access this via the formula tab in Excel) reveals that the range being specified here for the index function is 2007!G6:BL110.  MATCH("Subtotal."&$A$2, INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Modules"), 0) – here the row from which to return the value is specified. This is done via a match function that returns the position the text string Subtotal."&$A$2 (which is equivalent to “Subtotal.1.a”), within the Year.Modules range (cells C6:C110, again as shown by the name manager) on the 2007 year sheet. To summarise, this is effectively specifying that the appropriate value be returned from the row of the year sheet that is labelled Subtotal.I.a (i.e. row 80).  MATCH([Vector], INDIRECT("'"&I.a.Inputs[#Headers]&"'!Year.Vectors"), 0)) - here the column from which to return the value is specified. This is done via a match function that returns the position the Vector, here 1.a, within the Year.Vectors range (cells G6:BL5, again as shown by the name manager) on the 2007 year sheet.

In case of electricity storage what do you mean by peak power?  Is it the capacity of storage facilities (pumped hydro, batteries…etc.) or the possible peak power of peak power plants (natural gas based, below 1500 hours/a function)? (VII. c sheet)

~    The capacity of facilities

Regarding the electricity import-export balance why only the CSP import is taken into account? The fact that it is from CSP has any consequences on emission or not? In this latter case could we use it for any kind of electricity import? (plus please refer to questions 1-2) (VII. a sheet).

~    We assumed that electricity imports would come from concentrated solar power, as this seems to be a reasonable assumption for the UK. We do not include the emissions from this sector as the emissions occur outside the UK. You can use this sector for any type of electricity import – but make sure you reflect what is possible (i.e. would the exporting country need it for themselves?).

Would it be possible to apply trajectories to electricity network losses? Since in the modelling network losses are as fixed indicators.

~    Yes, if you think this is necessary. This would be simple to model if you can agree trajectories with stakeholders. This would be included in sheet V11.b.

On the "Energy flows" tab of the webtool, why do you show losses from thermal plants but not from other technologies such as renewables

~    The methodology here (http://2050-calculator-tool-wiki.decc.gov.uk/pages/28?redirect_from=Methodology) is consistent with that used in DECC's publication series Digest of UK Energy Statistics (DUKES).

Regarding the electricity production mix, where is it possible to feed into the modelling the natural gas and coal based capacities (and their trajectories)?

~    There is no assumed limit on the imports of gas or our capacity for gas-based generation in the UK. For coal, the model uses the current coal power and decommissions this over time. To incorporate a cap or trajectories on gas or coal capacities, amend sector “1.a”.

What is the default fossil fuel?

~    In the UK we assume our default fossil fuel is gas. This may not be the case in other countries  If you wish to develop a Calculator for another country, it is worth considering what it is reasonable to assume for your default fossil fuel (i.e. would it be gas like for the UK?)

How is the total electricity demand calculated? How is the supply-demand matched (are there enough capacities)? The difference then could be compensated with the export-import balance.

~    The user chooses how much electricity is demanded by selecting the effort to decarbonise in the demand levers. The Calculator then sums the electricity demand across the demand sectors. The Calculator meets this demand with supply.  Also see the answer to the question "Are the sectors connected (e.g. do supply-demand match)?" (number 8 in this list)

Do you account for the wind not blowing?

~    We have a stress test that tells you based on your electricity generation mix and back up capacity choices (interconnectors, pumped storage and EV demand shifting) how much extra back up capacity is required given a 5 day cold snap with little wind and peak heating demand. This scenario was based on past wind data and peak demand for heating and it represents the harshest test to the grid we found in past data.   For most pathways with high intermittent renewables, back up capacity options are exhausted over the 5 day period and back up generation (we have assumed CCGTs) is meeting the gap in supply and demand. Therefore, we believe this test is suitably harsh that enough back-up capacity is built to cover intermittency and peaking problems (please tell us if you have evidence of a harsher test).  However, there are two areas we would like to improve going forward:   •Better data on the frequency of intermittency   •Forecasts of weather going forward rather than relying on past data

## Bioenergy

How would we account for wood used for heating/cooking?

~    We don’t really use wood as fuel source in UK  We treat biofuels as being carbon neutral, so any carbon used is sequestered. This is an assumption we might revisit (based on some biofuels work recently within DECC), as it may be that overall emissions are higher than we assumed when starting this.  (RC to add note about India/other countries and how they’ve treated this)

You’ve included the technology of marine algae, does that exist in UK - has that been proven?  If not proven, why have you taken it into consideration?

~    There are many projects where we are still investigating if they're feasible - maybe in the same way as carbon sequestration it might be possible to work, but no-one knows yet for sure.  We've conducted some tests so far. The UK has a big coastline, so there was a lobby asking to include it in our model so that we can judge the effect in comparison to other options.  It’s another example where the team had to take political criteria into account, and include something that is significant to some key audiences of the tools even though the impact may be small or uncertain.

How is bioenergy treated

~    The emissions from burning biomass are counted as fossil fuel combustion and then exactly offset by a ‘bioenergy credit’. This has the effect of making bioenergy zero emissions, except if it is used in carbon capture and storage, in which case it becomes negative emissions.  For example, on this pathway: Pathway e0d…141  If you hover your mouse over the bottom-most blue bar on the right hand chart you will see that it is labelled as bioenergy credit -48 MtCO2e a year. This assumption is, of course, crude, because it assumes that:   1.There are no additional land use change emissions from the bio-energy   2.That the conversion of bioenergy from raw material to useful fuel is powered by bioenergy (so that there are no extra emissions in conversion).

Is it really possible to both increase land used for biocrops and increase livestock numbers

~    Q: The calculator assumes that it is possible to both dedicate 17% of land to the growth of biocrops, and increase livestock numbers by 10%. Is it suggested that this would be achieved simply through increased intensity of farming?  A: Yes. “Level 4” effort for “land management” assumes an increase in land allocated to biocrops of 38,160 km2 (so that 17% of land is used for biocrops) and an increase in land for forests of 10,913 km2. This is brought about by a 13,671 km2 fall in arable land for food crops, 32,812 km2 reduction in land for grassland for livestock and fallow and 2,589 km2 decrease in land for “other” uses. This implies an increased intensity of livestock farming.

What's the order of preference for biofuels?

~    RC to add answer from training slides

Within the calculator, you use the basic assumption that biomass can replace any fuel of similar physical state. Why do you do this?

~    RC to add answer from training slides

How is biomass allocated across the sectors?

~    For the UK, Biomass is produced in the spreadsheet as a result of a combination of user choices across a number of sectors.  The user specifies the amount of domestically produced biomass and how they want this to be converted into different forms (a mix of gaseous, liquid and solid).  This is combined with imported biomass to provide the total available biomass  This total biomass is then used up by the sectors that use the corresponding end use forms of fuel.   When the user selects options that need a solid fuel in the Calculator, the fuels available are used up in a particular order, as follows: domestic biomass and imported biomass; then domestic coal; and finally imported coal. If a preferential fuel type is not available then the Calculator uses the next type. The same order of preference is assumed for oil and liquid biomass and for natural gas and gaseous biomass, where biomass is used ahead of fossil fuel sources when it is available.   (can we add anything interesting about how other countries have done this?)

## Buildings

Where is public street lighting included? Where could they include it as an option?

~    In the UK Calculator we only refer to “commercial lighting” in general i.e. all lighting that is not in the residential sector (and is dealt with in X.b in the Excel). There is not a separate breakdown for public street lighting. If you would like to refer specifically to street lighting you will need to include data on the electricity that this currently consumes, and different scenarios for how this could either increase or decrease depending on technology choices.

As you know, Mr Khanh-Excel expert developed excel files for input data (data requirement) of each sector (energy demand side and supply side) that based on most of IESS-2047/India case. And then Mr Hoang Anh posted data on the Excel - data requirement-Resident- Cooking and Hot water sheet, We (Khanh and me) have reviewed and found that the Technology Efficiency of all energy/electricity devices/stoves is 100% (with approach based on energy demand in term of useful - see the attached). And then we also checked the India case. The situation is also the same, even the Technology Efficiency is more than 100% (please check XIII.a-Excel file -India case).

~    1. Technology efficiencies: I think some confusion may have arisen regarding the technology efficiencies. As you can see from the excerpt below from the UK model, we make use of both input and output efficiencies. In this instance the efficiency we’re concerned about the output efficiency; in terms of the amount of heat we get from the electricity used. These are shown below in the H.01 column. Most of these are below 100% (e.g. Gas boiler old: 76%), except in the case of heat pumps, where the efficiency is exaggerated as environmental heat is also used. In the table below, the input efficiencies shown, which effectively show the input energy source, are commonly 100% (e.g. a gas boiler uses 100% gas). I suspect these input efficiencies may have been confused with the output efficiencies. I’m not sure about the implementation in the India Calculator; we will discuss this with the team there.

I am now going through sheet IX.c commercial heating and cooling and have difficulty understanding the section on technology efficiencies in there (from line 96 down),   Could you pls. explain their nature, in particular while some are negative and the other are positive and their magnitudes

~    Some of the efficiencies represent energy inputs so have a negative sign some are outputs, so have a positive sign. For example, in the case of ‘Gas boiler (old)’, the energy input, gas V.05, has a negative sign (100%), while the outputs, heat H.01, 76%, (76% of the input energy is converted to heat), and losses X.01, 24%, are positive. The idea is that the output tables always net to zero, with the positive and negative values cancelling each other out.  Some of the magnitudes are very high (e.g. for heat pumps) because the efficiency is quoted in terms of the electricity used (i.e. the fuel input that we care about), while in reality they also make use of a secondary energy input, environmental heat.

How does the modelling take into account the different housing types (block house, family house, public buildings…etc.) in the building stock? They can differ very much in respective parameters and insulation.

~    We have estimated the thermal leakiness of our housing based on a separate analysis of the housing stock of the UK (which takes into account the level of existing insulation, the building materials, building shape and size and so on).

On sheets IX. a and c what is the meaning of the technology codes (in rows 75 and 93) and the percentage in the columns? It seems like the codes do not follow any logic.

~    The codes correspond to a lookup value to select a combination of electrification and non-electrification energy source (in the table at rows 15 -21).

The spread of district heating could decrease heat related emission considerably. How is the ratio of DHC supplied buildings taken into account? How is the fuel (gas, coal, RES) for DHC generation taken into account?

~    The ratio of DHC supplied buildings considers what is physically possible within the UK. District heating has no emissions in the heating sector as the emissions are counted in the power generation sheets, depending on the type of fuel combusted.

Is the cooling demand (TWh) reflected in the electricity generation mix (summer peak load)? (Sheet IX a)

~    There are user trajectories for the cooling technology which affects the energy demand in the heat sector. This demand affects the energy supply and so it can affect the generation mix (see answer to question 2)

I expected altering the level of insulation to make a bigger difference

~    The difference in greenhouse gas emissions from the all at level 1 pathway[1] and a pathway whose only difference is level 4 effort on insulation[2] is only 3% of 1990 levels. This may appear smaller than expected. See the answer here for more detail:  http://2050-calculator-tool-wiki.decc.gov.uk/pages/124  It is worth noting that the calculator does not capture the full benefit of insulation. In particular, insulation may have a significant impact on the need to provide 'peaking' electricity.

Why does reducing thermal waste in all domestic buildings by 50% by 2050 have no apparent impact on oil use?

~    In the UK's 2050 Calculator, in the baseline year of 2007, oil-fired boilers account for 4% of heating technologies.   If the user of the 2050 Calculator reduces thermal waste in domestic buildings using the “home insulation” lever, this reduces oil use in the years 2010- 2045 (the 2050 Calculator assumes that oil boilers will be phased out by 2050). A 50% average reduction in thermal leakiness reduces oil use by around 0.3 - 1.3 TWh per year over the 2010 to 2045 period.  This reduction in oil use does feed through into the graphs in the 2050 Calculator Webtool and spreadsheet but it is not noticeable for two reasons:   1.The 2050 Calculator assumes that oil boilers will be phased out by 2050. Therefore, a reduction in the thermal waste of domestic buildings of 50% by 2050 will have no impact on oil use in 2050 in the 2050 Calculator; and  2.The reduction in oil use is small relative to the total oil use.     Energy supplied by oil and petroleum products is given in row 43 in the spreadsheet in the “Intermediate output” worksheet. The spreadsheet can be accessed here: http://www.decc.gov.uk/en/content/cms/tackling/2050/calculator_exc/calculator_exc.aspx

How does the user determine the level of district heating?

~    The level of district heating to provide heat to domestic and commercial properties up to 2050 is determined by the user as follows:   1.Domestic heating:   •the user selects the level of electrification of domestic heating up to 2050, by using the “home heating electrification” lever (National Grid have selected level 4, the highest electrification); and   •the user selects the level of district heating for homes that are not electrified by 2050, by using the “home heating that isn’t electric” lever (National Grid have selected level A, where gas or gas CHP are the dominant non-electric sources).   2.Commercial heating:   •the user selects the level of electrification of commercial heating up to 2050, by using the “commercial heating electrification” lever (National Grid have selected level 4, the highest electrification); and   •the user selects the level of district heating for commercial properties that are not electrified up to 2050, by using the “commercial heating that isn’t electric” lever (National Grid have selected level D, which uses a mixture of non-electric sources).

What are the exact numbers in Figure A3 in the 2050 pathways report for the levels of domestic lighting and appliances in 2007; 2010; 2020; 2030 and 2050

~    The TWh per year usage figures for sectors, for a given pathway and a given year, can be found as follows:   domestic lighting and appliances: cell H17 in each of the “year” worksheets (worksheets “2007” to “2050"  In order to get the energy demand under each a given trajectory (1 – 4), you will need to set the trajectories to either level 1, 2 3 or 4 in the “Control” worksheet, column E.

Where did the u-values in the heat sector (IX.a) come from?

~    Typical U-values for various measures, for example, cavity wall insulation (by M2) are combined with the proportion of properties by age that have these measure (using data from the English House Condition Survey, by the UK's Department for Communities and Local Government). These are then combined with information about the housing stock, e.g. wall area, to produce average heat loss estimates.

What is pumped heat on the Sankey diagram

~    The Sankey diagram shows 'pumped heat' as a fuel source. This is the heat that a heat pump (a type of heater for homes and businesses) sucks from the atmosphere or ground and pushes into rooms.

How can we work out the energy needed for cooling?

~    The first thing you need to do is work out the amount of cooling demanded. This will mean working out the average external temperatures, and then you can compare this against the temperature people want their homes to be at  You can then convert into type of energy, and work out the amount of fuel required (electricity, or for heating this might be gas)  That's where capture improvements, by putting all appliances into single sector

## CCS

What is the connection between sheets I b. and XIV. a regarding CCS? Is it not over determined? Once we know the capacities supplied with CCS and their parameters the captured CO2 can be calculated. Why is sheet XIV a necessary?

~    I.b is CCS on power stations.  XIV.a is stand alone geosequestration (for an explanation of the technologies, see page 237 of: https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/68816/216-2050-pathways-analysis-report.pdf)

## Conclusions

What feedback did you get through the call for evidence? How did this feed into the model?

~    Our part 2 2050 calculator document gives lots of detail about sectors where we had feedback, and how the 2050 Calculator was changed because of it:  https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/42545/1344-2050-pathways-analysis-response-pt2.pdf    You can see documents with all the feedback we received during the call for evidence here:  https://www.gov.uk/government/consultations/2050-pathways-analysis

Does the UK calculator show we really need to increase electricity generation from todays levels to hit the 2050 target?

~    From the UK's 2050 pathway analysis to date, there is a clear trend that most pathways involve a large increase in electricity generation: 13 of the 17 involve an increase of more than 20% on 2007 production, and half of the pathways more than double. The consequences of not electrifying sectors and therefore not increasing electricity generation would be large requirements for bioenergy and heroic levels of behaviour change to reduce per capita energy consumption.    Therefore, although it is physically possible to reduce electricity generation and reach the UK's 2050 target, it involves a large amount of heroic effort on demand and bioenergy that many stakeholders consider unrealistic. An increase in electricity generation has been one common message of the pathways analysis to date, and indeed work from the CCC and economic models, such as MARKAL, indicate a similar trend. As the department works towards producing a narrower set of plausible pathways, then we could begin answer with more certainty, but until then it remains true to say that the 2050 work indicates a need for an increase in electricity generation in the majority of pathways presented, with many pathways more than doubling current generation demand.

## Cost

For CHP, do you include the saving in producing electricity as well as heat

~    Yes, the spreadsheet includes both of these.

Do you account for the damage cost of carbon?

~    Not at the moment.

How are you accounting for the macroeconomic impact of climate change?

~    We don't include the impacts of climate change in the model.

Why have you included the total cost of vehicles?

~    "On the cost methodology, it appears that the total cost of vehicles in the transport sector is included. While one could understand including the incremental cost of, say, electric vehicles or plug-in hybrids over "conventional" petrol or diesel cars, to count in the total cost of the vehicles seems illogical."    The calculator give the user the option of choosing to travel less, and to travel differently (for instance, for a greater proportion of journeys to be by train or bicycle thank today). To fully account for the cost impact of this option, and its interaction with the choice about what sort of vehicle is used (conventional, electric or hydrogen) the total cost of vehicles was included.    Note that, at the moment, the total cost of aircraft and ships are not included.

How can one see the costs sections of the analysis on the webtool

~    The costs part of the analysis can be found by clicking on the "see implications" button in the top left corner of the webtool window. There are three different costs pages which can be chosen from the drop-down menu this button prompts.

You appear to have costs and cost ranges for 2010 and 2050, what are the costs you use for the intervening periods?

~    The period between 2010 and 2050 is broken down into nine five year periods in the Calculator. We use one cost for each of these periods.   This cost is generally calculated by linearly interpolating between the 2010 and 2050 figures - that is to say for the middle period, 2030 to 2035, the cost will be half way be between the 2010 and 2050 costs; for the fifth period the cost is five ninths of the way between the 2010 and the 2050 costs.   In the case of the power sector we have followed the way the costs fall in the MARKAL model. The costs do not change in every period from this source, with typically three or so "vintages" of costs. For example one cost for the 2020s, another for the 2030s and then a third for the period after 2045.   The actual numbers for the costs and the calculations involved can be found in the excel spreadsheet version of the model, although the 2010 and 2050 costs displayed on the wiki give a good approximation of the trend.

Have you used a discount rate? What have you used if so?

~    The costs we are currently presenting in the webtool and the excel model are not discounted.  However, the excel spreadsheet model has the functionality to easily enable a discount rate. This can be done through the "Global Assumptions" worksheet. We have a 3.5 percent default loaded for this purpose. The reasons for this can be found on the Discount rate methodology page: http://2050-calculator-tool-wiki.decc.gov.uk/pages/107

Why are you using total costs to society rather than tax, subsidy and costs to consumers

~    The Calculator works out the total costs to society as a whole of pathways generated by users essentially because working out the impacts of specific policies in terms of taxes or subsidies, and the costs and distribution of these policies, is beyond the scope of the model. The 2050 Calculator is intended to be a simple model; it does not model the markets and relationships which would be needed to work out this level of detail. Furthermore, the Calculator is designed to be policy neutral. The model does not inform on how pathways might be achieved, only the potential for what could be achieved. For this reason, it is more consistent to calculate costs at the broadest level.

Does the 2050 Costs calculator account for system costs?

~    We have accounted for system costs and intermittency in the 2050 Pathways analysis, although any further evidence or comments on how we can improve our cost sources and methodology would be greatly appreciated.  See this page for a detailed answer:  http://2050-calculator-tool-wiki.decc.gov.uk/pages/220

How do you treat discounting?

~    We have included discount rates once costs within each time period is calculated. This allows us to vary the discount rate based on different opinions on what the right discount rate should be used. Of course, other ways of presenting costs such as %GDP may mean discount rates may not be used (see Web interface). For more detail, please see our methodology section.

how do you treat financing costs

~    Financing costs are a variable which can be defined by technology in the excel, both in terms of interest rate and duration of loan period. The question is how to present finance costs in the webtool, please see web interface to leave your thoughts and comments.

Why are the cost ranges so large?

~    Our initial approach has been to create a large cost range, encompassing all credible experts opinions and forecasts of costs over time. At this stage we have not attempted to add probability distributions to future costs, since we do not believe there is sufficient data or evidence in most cases to achieve this.    We wish to capture all credible experts views on costs, however if there are some cost estimates used which are widely discredited, please comment on those sources and add other cost sources. Equally, if you believe costs will fall with some certainty from today's 'high' estimates please also inform us.

Do you account for nuclear waste costs?

~    We have added a cost of uranium disposal and plant decommissioning as a function of the Uranium used in pathways. See Uranium Enrichment & Disposal cost data at: http://2050-calculator-tool-wiki.decc.gov.uk/cost_categories/20

Presumably if energy prices are rising people will demand less. Do you account for these dynamic feedbacks?

~    There is no price elasticity function, which adjusts energy demands in response to prices in pathways. This is because the pathways are user led and the costs work, emissions and energy are shown as consequences of a users chosen pathway. Therefore, in a high-level way a user can decide to replicate demand side response by increasing the level of demand reduction through the user choices but we have not hard-wired this response, since the 2050 Calculator has no optimisation function

How will you measure the impact on bills?

~    The model doesn't measure the impact on consumer bills. It works out the cost to society of a particular energy system, but doesn't specify who pays.

1. Finance costs – why are there different years attributed here.

~    The finance costs (‘Global assumptions’ row 31 onwards) are made up of two factors: the interest rate, and the period of time a loan is structured. This is to reflect the typical period of time loans are taken out for in an industry. The shorter the time period – the less interest you have to pay.

## Emissions

The calculator uses an average CO2 emissions factor for solids, liquids and gas, how did you reach this value?

~    I believe that, for CO_2, we used the specific emissions factor for the particular fuel listed in the table. (Eg, for solids, we used the emissions factor for industrial coal). These emissions factors are reported in DUKES (the Digest of UK Energy Statistics, published by DECC).     It turns out that emissions factors expressed as emissions per unit of energy (rather than per unit of mass or volume) are reasonably constant for all hydrocarbon fuels of a particular physical state – certainly within the limits of uncertainty expected of a model like this.    For the other gases, CH_4 and N_2O, we used the ratio of these gases emitted to CO_2 emitted from combustion (of the appropriate fuel) for the total UK emissions, as reported in the Greenhouse Gas Inventory, and assumed this ratio applied to all sources. In summary: for each physical state of hydrocarbons, we first estimated CO_2 emission as above, then applied a constant multiplier to obtain the emissions of the other gasses.

Why are some emissions negative?

~    In the emissions chart in the “Control” worksheet, you will see that some emissions are negative. The technologies that have particular characteristics that result in negative emissions are as follows:   • Carbon capture and storage (CCS) – when gas is burned in a CCS power station, the Calculator applies the natural gas emissions factor to the quantity burned and adds the resulting CO2 to the model’s total emissions. To account for the fact that these emissions are captured, an equivalent negative quantity of emissions is also added to the total.   • Biomass – like all other fuels, when biofuels’ biomass are combusted, the model applies an emissions factor according to its physical state. However, unlike hydrocarbons, biofuels do not produce any CO2 when burned. UNFCCC accounting guidelines state that countries should treat biomass as an emissions neutral energy source. This is because carbon from the atmosphere is sequestered into the biomass while the feedstock is growing. To account for this, an equivalent negative quantity of emissions is included in the emission calculation. When biofuels are combined with CSS, the above treatments combine, resulting in a negative contribution to the overall CO2 emission calculation.   • Geosequestration - these technologies remove CO2 directly from the atmosphere and store it in parts of the geochemical system. The amount of CO2 removed appears as a negative quantity in the emissions calculation.

## Fossil fuels

Regarding the energy supply side, i need your support to have information and some data in term of general on oil refinery, i.g. i). refinery losses; ii). Energy own use in the refinery plant (electricity, heat, and oil products for processing, etc.); and iii). O&M cost-Refinery plant. Because, there is not available, confidence information and data on that although one oil refinery plant is operating with capacity at 6.5 mill. ton per year. I have to say that the data is not confidence enough due to the data collected from energy statistic that mentioned the refinery losses is 12%?

~    1. Refinery losses: Just to check that we understand the question – there is one refinery in Vietnam, but the data they have is confidential. You are looking for information on what assumptions you should use for costs and losses.    If the refinery is not absolutely huge, then you are probably ok using UK data for refineries (sheet XVa. in the UK Calculator).    The other option is to use data from a neighbouring country, or if that is too difficult to obtain you can use US data from the MARKAL user guide. We’d recommend using UK data, unless you think that this will really distort your results.

I have one more question which is about oil refinery module (XVa). I understand from the UK model that output products are not separate by types of fuel i.e., DO, FO, Gasoline etc. Could you pls. explain why it is so?  Secondly, I do not see how these output are used (row 129). Could you pls. explain?

~    The Calculator takes a simple approach where total energy demand and supply within the UK are calculated separately, and any difference between them is balanced with imports/exports. There is no attempt to show the path from extraction, to conversion and then consumption within specific sectors.  In the case of liquid hydrocarbons, as were the focus of your question, the total requirement is calculated in row 101, ‘Subtotal.XVI.a Requested hydrocarbons’ (e.g. 830.4 TWh in 2010) of vector V.04.  This demand is met with domestic production via sector XV.b, (802.5 TWh) , with the remainder (27.9 TWh) being supplied via balancing imports in vector Y.05. These quantities enter via vector C.02, and are transferred to vector V.04 via the ‘fossil fuel transfers’ sector (XVI.a), so that supply and demand for sector V.04 net to zero.  Sector XV.a is essentially a subsidiary sector that exists primarily to calculate the costs, energy requirements and emissions associated with refining the domestically produced fossil fuels. The energy inputs and outputs of have already accounted for as described above.  To maintain simplicity, the Calculator treats all liquid hydrocarbons the same, whether they are diesel or petrol etc. The fact that the emissions factors for these different fuel types are, on an energy basis (i.e. MtCO2/TWh), essentially the same, enables this simplified approach to work. Diverging from this approach would add a great deal of complexity to the Calculator.

There are lots of types of coal - which type are you comparing to?

~    In the UK’s 2050 calculator, there are only 3 emissions factors: solid, liquid and gaseous hydrocarbons.  The emissions factor work on a ‘per unit of energy’ basis, which means that all fuels of same physical state have same emissions. These wouldn't be the same on mass, but on a TWh basis, works the same.  So because this is done on an energy basis, we can use same emissions factor on all hydrocarbons. This is a very small simplification, applied generally, which keeps things a lot more manageable  So each type of hydrocarbons goes to the end use, and is not allocated to specific sectors. We just make a subtraction from solid, liquid gas, and then there's an adjustment made

How is shale gas treated

~    (From wiki page, written by Jan Kiso)  In December 2010, we updated our 2050 Pathways calculator to include costs estimates for the different choices facing the UK’s energy infrastructure . Although there are inevitably uncertainties about predicting costs of anything decades in the future, we felt that in order to have an honest and fair discussion about the UK’s energy future we needed to reflect the potential costs.  Since then the 2050 Pathways team have received comments about how shale gas is treated within the 2050 Pathways Calculator, with some people expressing concern that we were ignoring this source of energy.  Shale gas is a natural gas (predominantly methane) found in shale rock. Natural gas produced from shale is often referred to as ‘unconventional’ and this refers to the type of rock in which it is found. ‘Conventional’ oil and gas refers to hydrocarbons which have previously been in sandstone or limestone, instead of shale or coal which are now the focus of unconventional exploration.  The 2050 Pathways Calculator does not distinguish whether natural gas in the pathways originates from ‘conventional’ or ‘unconventional’ sources. It takes natural gas as a primary energy source.  If the Calculator user believes that shale gas will significantly lower the price of natural gas in the UK in the future, he/she can choose lower cost assumptions in the Calculator section ‘costs sensitivity’. Users could look at the impact of gas being 45p/therm to 100p/therm in 2050. These high/low gas prices are taken from the DECC fossil fuel price projections published in October 2011.  The Calculator has no constraints on the amount of gas the UK can use. For example, in the “do not tackle climate change” scenario (defined as all level 1s), 66% of energy supply in 2050 is natural gas. The Calculator just assumes that gas imports are available.

Why are oil demand projections from the DECC energy model so different from the 2050 analysis?

~    The 2050 Pathways and the Energy Model are two separate models, and there is very little overlap in inputs. That explains why you are seeing different projections in oil demand.    You can read more detail here: http://2050-calculator-tool-wiki.decc.gov.uk/pages/219

It is very confusing having energy supply from coal and from biomass represented by the same block on chart two

~    The “UK Primary Energy Supply” chart in the 2050 Calculator Webtool shows the energy supplied from the available primary energy sources in the Calculator: the “coal” line shows the energy derived from coal; the “bioenergy” line shows energy derived from biomass. However, choices on solid biomass have an impact on coal use and this will be visible in the chart. This is because energy demand is always met in the 2050 Calculator, and if insufficient biomass is provided the corresponding fossil fuel is used. For example, if the user selects a higher level of biomass power plant deployment, then coal use will increase if there is insufficient solid biomass in the user’s pathway to satisfy the solid hydrocarbon demand.  A detailed breakdown of the energy supplied from the different sources is provided in the spreadsheet in the “Intermediate output” worksheet, rows 23 to 47. The spreadsheet can be accessed at: http://2050-calculator-tool-wiki.decc.gov.uk/pages/140

How does the fossil fuel production (NOT use) affect emissions? (sheet XV b)

~    Fossil fuel production affects emissions in two ways: (1) from mining (fugitive emissions), and; (2) the energy required in the production process.

## Industry

How were the UK's industry sectors defined: what is included and what isn't included?

~    To understand more about the UK's industry sectors and how these are classified, you can have a look at our part 2 2050 calculator document (pages 90-92 summarise how the levers for industry were changed from one to two levers):  https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/42545/1344-2050-pathways-analysis-response-pt2.pdf    The link below also gives a summary of how industries are assigned to the categories we use, so this might be a helpful check for you.  http://2050-calculator-tool-wiki.decc.gov.uk/pages/131

Is the industry emissions (and energy use) matched with the actual electricity generation mix? (on sheet XI. a. the electricity need of the industry is used as input – what is the fuel mix behind this electricity need?)

~    See question 8

Could you please indicate which industries belong to certain categories (chemicals, minerals, metals)? Is the refinery factor included in one of them? Why there is a distinct sheet for refineries (XV a.)?

~    See the full answer here: http://2050-calculator-tool-wiki.decc.gov.uk/pages/131

Why is the growth in energy demand multiplier indicator missing between 2025-2050? (sheet XI. a)

~    The energy demand multipliers are annual multipliers for the years 2007 – 2050 (whereas the output index has a growth rate for 2007- 2025 and then 2025 to 2050)

Where is industrial CHP

~    Industrial CHP is included, but it is not shown separately. Instead Industry as a whole is modelled as taking in fuels (gas, coal, oil, electricity, some heat from district heating) and then do useful stuff with it, including turning it to electricity and heat for their own use.   At some point, we'd like to separate out industrial CHP.

Is it possible to use baseline year other than 2007? (sheet XI. a and other sheets also)

~    Yes, you can start from any base year. We used 2007 since it was the most recent data point at the time of development, but other countries have used other years (for example 2010). It's important that you have as much data as possible for the year that you choose as your base year. You want the year that is complete enough, but also recent enough.

## Nuclear

1. Nuclear – 3GW “peak” plant. What does this mean?

~    “Peak” plant (II.a row 71 in the Excel) is used to describe the size of each nuclear plant included in the nuclear scenarios. We refer to “peak” to show the maximum generating capacity of the plant, which the way that the industry talks about plant size. This is then combined with a capacity factor to calculate how much electricity it can generate.

## Renewables

For Wave and tidal energy what does availability factor mean?

~    2. Wave and tidal energy. What does “availability factor” mean?  “Availability factor” (III.a rows 67-71 in the Excel) is used to model the fact that you will need to maintain these renewables at some stage. Some more general background on this and the difference between availability and capacity factors is here: http://en.wikipedia.org/wiki/Availability_factor   An availability factor of 90% shows that of a development of 10 wave installations, at any time 1 will not be generating electricity because it is closed for maintenance. A higher factor e.g. 95% shows that more installations would be available to generate electricity e.g. of 10 installations at any time 0.5 will not be working.

## Sector sheets

Is it possible to turn a fixed assumption indicator to trajectories?

~    Yes: you can have any number of trajectory assumptions, within the limits of what is practical. Remember that it will make it harder for the users to understand the model if they have to make lots of choices; we have found that around 40 choices is about right. If you create more trajectories it also requires more stakeholder work to agree the range of change in that trajectory. You can combine multiple trajectory parameters within one lever (for example, occupancy and efficiency in the transport sector) but this becomes more opaque.

## Summary sheets

Are the sectors connected (e.g. do supply-demand match)?

~    Generally, all the sectors are independent. The user chooses what happens in each sector, and the Calculator adds up the supply and the demand for energy in the “year” worksheets (for example, worksheet “2007” summarises the supply and demand for energy for 2007). However, If there is a shortfall of supply from domestic fossil fuel production, domestic nuclear, biofuels and renewables production, electricity imports and bioenergy imports, the Calculator “imports” gas to meet the excess demand. The other interactions are:  · bioenergy (see page 13 of the “How to Guide” https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/65606/6966-2050-calculator-spreadsheet-how-to-guide.pdf)   · fossil fuels (refinery activity, worksheet “XV.a”, depends on the amount of indigenous production of oil, as specified by the user.

## Technical

How easy is it to add air quality?

~    For the details on air pollution, look at the “air quality” sheets in the Excel. They come after the costs work, and all start with AQ e.g. ‘AQ Outputs’. Here’s detail on the methodology – as Johanna mentioned it would be possible from this to work out the direct impacts on health. For other co-benefits we have attempted to add biodiversity impacts to the UK Calculator to the UK Calculator, but this has been very difficult due to lack of data, and the complex nature of the issue. We have been more successful adding water consumption of each pathway, and would be happy to share with you the methodology there (as we mentioned, it is not yet published in the live spreadsheet). Any work on co-benefits brings extra work, so happy to provide guidance on what this might mean for you if you want to add anything.

What is the reason behind the distinction between primary and secondary energy? Would there be problems if the Colombian team wanted to change these definitions?

~    Primary sources refer to energy vectors in their initial state as they enter the system. Secondary sources refer to any primary source that may have undergone a change of state, before it is consumed e.g. solar electricity – electricity from the grid. These vectors (both primary and secondary) aim to be mutually exclusive and comprehensive of the whole energy system.    It would be ok to change definitions to better fit Colombian statistical conventions, but you would need to be very careful that you were not going to double count anything (e.g. make sure everything is mutually exclusive). If you wanted to add any additional primary or secondary sources as vectors in the technology sheets, and then also add these to the year sheets.

How do I find out more about structured table references?

~    This section of the book explains in detail what structured table references are, and how to use them:  http://book.2050.org.uk/calculator-book/appendix-2-complex-excel-formulae.html#structured-table-references

How does the new (as of July 2014) webtool production process work?

~    Here's a quick summary list of the required webtool production steps:    1. install Ubuntu 12.04 64 bit  2. run the set up script https://github.com/decc/twenty-fifty/blob/master/util/setup-ubuntu-12.04.sh  3. (run bundle exec rake, and see 0.0.0.0:9292 to check if the UK version runs properly)  4. start a new branch / fork (might need to look at git help to see how)  5. edit the spreadsheet to contain the named ranges (see the more up to date versions, e.g. 3.6.0 of the UK model for inspiration - and please ask the UK team for help if you need to)  6. replace the spreadsheet in the model folder with the Colombia version, and name it model.xlsx  7. edit data_from_model.rb to list all of the relevant named ranges  8. run model/translate_excel_into_c.rb $ruby translate_excel_into_c.rb  9. run model/compile_c_version_of_excel.rb $ruby compile_c_version_of_excel.rb  10. bundle exec rakup (starts the local server)  11. navigate to 0.0.0.0:9292 in your browser    Assuming this all works, the nest step is to make cosmetic changes to the front page by editing index.html.erb, and then the JavaScript files if you want to change the charts.

We would use 2010 as base year and then use the standard incremental steps of 5 years, plus maybe adding 2012 as first simulated year for comparison (i.e. what in the UK calculator is 2010).  I can't seem to recall if this must be done by editing all sheets by hand and updating the trajectories accordingly, or if there is a "master" location where this editing can be done.

~    To edit the time periods covered, each sector sheet must be edited individually.   There isn’t a master location for setting this.

The series of "DUKES" sheets is, as far as I can figure, mainly a central database which is referred to in other spreadsheets. Assuming that all references in all sheets are updated with the correct numbers, is it safe to remove these sheets? This is part of my effort to produce a lighter, hopefully faster version of the workbook, and according to the Wallonia version it seems possible to do so (their numbers are written directly in the sector sheets, as far as I can see).

~    The ‘DUKES’ worksheets are from the department’s ‘Digest of UK Energy Statistics’, a publication covering all the main aspects of the UK energy system. We decided to include these worksheets within the Calculator workbook so that users could more easily see where our base year numbers came from.     Whether you maintain this aspect is a decision for you and your team, but please take note the transparency issue.

We have 20 years of data where we've reflected energy consumption, demands, and of course emissions. If we take this baseline then hopefully calculations will match the baseline data we have got. Should we include historic data in the tool?

~    The historic emissions are used as a starting point for many trajectory assumptions. So for example, if we look at domestic transport starting in 2007, levels 1 to 4 dictate what happens from that point onwards. The user has the opportunity to say what will happen to demand afterwards.  In terms of including historic data, with hindsight maybe this would have been good idea. Historic data would help the user when they're trying to determine chosen pathway to see what happened historically. This is what we have done in some of the one-pagers: for example, showing the rate of nuclear build in various countries historically, which helps to show how ambitious the UK’s levels 1 to 4 are.  It's possible to have as much historic data in calculator as you like. You just need to pick date in history where that stops and modelling starts.

The INDEX/MATCH formulae used to look up data are so complicated! Why don't you just use VLOOKUP?

~    RC to write

Are all the numbers and calculations inside the sheets are accumulated for five years, or is it only data of each year?

~    The aim of the year sheets within the calculator is to give a picture of how the energy system looks in each of those years - e.g. the year 2040, 2045 etc.   In each of these, we work out all the input data and assumptions and all of the outputs just for that year, so all numbers should be by year unless it’s specifically stated otherwise.  Occasionally calculations are by 5-years (for example when working out the new capacity that will be added between one year and 5-years later), but the units should indicate that.    A couple of ways the sheet is designed around this by-year approach are:  • The base year calibration (2007 in the UK’s case) which matches up actual reported figures for that year, against modelled figures  • In the Intermediate output sheet : the heading (D4) says TWh per year  • And anywhere that cumulative calculations are done, approaches such as the following are taken:  “Cumulative emissions are estimates based on a linear trajectory between the 5 year time periods” (e.g. intermediate output sheet, cell C198)

Could you please explain me or send to me the document with the detailed information of vectors?

~    http://en.wikipedia.org/wiki/Primary_energy

Can we add new vectors? If so, how?

~    These vectors (both primary and secondary) aim to be mutually exclusive and comprehensive of the whole energy system. It would be ok to change definitions to better fit Colombian statistical conventions, but you would need to be very careful that you were not going to double count anything (e.g. make sure everything is mutually exclusive).  You would need to add any additional primary or secondary sources as vectors in the technology sheets, and then also add these to the year sheets. We’d be happy to advise if you do decide that you’d like to add any new vectors, just to make sure that there are no conflicts with anything else.

Apart from the level of accuracy of statistic input, what has been the criticism or main weakness of this model?

~    Some people think that there are technologies or choices not included which should be, for example more options in transport sector to lower demand. Ideally level 4 should be very ambitious, and roughly equal effort across all sectors - although we're not quite there yet in the UK version, we recommend that you use your stakeholder consultations to do this.  We receive complaints asking where shale gas is within the model, and asking about options to increase domestic gas in future (however several other countries have made it easier to increase production of any fossil fuels)  People also sometimes like to be able to change more than just the levers – for example, when a particularly technology will be launched. However, because the fixed assumptions are always in the Excel file, some people have adapted this to explore questions of their own.  Finally, people sometimes ask what do we do with all public comments and how can people feed into the model. Although we invited comment through the Call for Evidence, there is always more we would like to do here.

Does the model include the impacts of climate change on water levels?

~    We don't have any climate feedbacks currently in the model, as there are still many uncertainties. If that's something you wanted to explore, it would be very possible to build into worksheets, however the problem would be getting data good enough.  Our team's Global Calculator could now help you to explore climate impacts of global choices though. The webtool is available at the link below (along with the spreadsheet and other supporting materials): http://tool.globalcalculator.org/

For teams working on the Calculator so far, what aspects of the UK structure have they most needed or wanted to change?

~    In general, teams have made fewer changes to the renewable supply sectors – they have removed some technologies, and sometimes merged technologies (e.g. treating onshore and offshore wind together), but broadly they have left the same.  For fossil fuel production and generation, there have been some changes: for example, several countries have changed the default fuel to coal (rather than gas as used in the UK).   For demand sectors, there has often been more change. For example, within transport the Chinese calculator team have made a few big changes. They’ve divide transport into urban and rural to reflect the very different patterns of travel, and the shorter distances travelled.  In your transport sector, you’ll also need to think about what you want to include and how you want to split it. You could also decide to include international transport, even though not accounted in official inventory, because you often need to consider implication of those data when discussed internationally.

What programming software/tools do I need to update the webtool or wiki?

~    The web front end requires the open-source Ruby language, and JavaScript.

If I want to recompile the tool, how to do I do this?

~    If you change the spreadsheet, and wish to recompile it for the web front end, you will need Ruby, a C compiler, and the decc_2050_model gem from http://github.com/decc/decc_2050_model

Where do I find the Excel model?

~    The Excel model is self contained and available here:   http://2050-calculator-tool-wiki.decc.gov.uk/pages/140

How does the 2050 pathways model relate to other energy models

~    The short answer: There is no perfect model. The 2050 pathways model is playable & transparent but simplistic. Markal, ESME, the DECC Energy Model are rich & powerful in different ways but complex and limited in others. DECC uses all four.    For a longer answer, see the page here:   http://2050-calculator-tool-wiki.decc.gov.uk/pages/60

Why doesn't the spreadsheet work in older versions of Microsoft Excel or in other spreadsheet programs such as open office

~    The only software that the Calculator can run on is Microsoft Excel for PCs 2007 and 2010, and Microsoft Excel for Macs 2011.   The reason is that the model includes “structured references” and these have not been implemented in earlier versions or in open source Excel alternatives.   Possible work arounds:   •Download trial copies of the latest version of Microsoft Excel   •Programmatically drive the ruby version of the calculator, distributed as part of the source code to the web interface

Is the 2050 Calculator an optimisation model?

~    No, the 2050 Calculator is a user driven model. The user specifies energy supply and demand across the economy by selecting effort levels for around 40 sectors. In this respect, the Calculator is fundamentally different from cost optimisation models such as MARKAL. Models such as MARKAL examine the costs of different technologies and work out the least cost pathway to achieving an emissions reduction target.  It is possible to identify low cost pathways using the Calculator, but the user has to do this manually through an iterative process. An example of a very low cost pathway is the Analogous to MARKAL pathway (http://2050-calculator-tool-wiki.decc.gov.uk/pages/170 describes a representation of a least cost pathway from MARKAL).  However, if you wish to use the 2050 calculator as an optimisation model, you can. You need to use the code from here: https://github.com/decc/decc_2050_optimizer

Where do I find the source code?

~    The source code for the web front end is available here: http://github.com/decc/twenty-fifty  The source code for this wiki is available here: http://github.com/decc/twenty-fifty-wiki

What version of Excel do you need?

~    The Excel model requires Microsoft Excel, 2007 or later (sadly it doesn't work in Open Office or older versions of Excel, because of its use of structured references).

Who do I contact for technical help?

~    If you want to talk about what you are trying to do, or find out about our experiences in developing the tool, please get in touch at 2050pathways@decc.gsi.gov.uk

As another country developing a calculator, what *stress test* should we use to examine balancing needs?

~    In the UK we use an example of 5 days of bad UK weather (no sun so no solar energy, no wind so no wind energy, cold weather so high heat demand). Think about what a "period of bad weather" might look like in your country?

As another country developing a calculator, what *sectors* might we need?

~    In the UK Calculator we include sectors which correspond to energy options that may not exist in your country. For example, do you have any tidal stream potential? If not, remove the sector.

As another country developing a calculator, what technologies might you need to include?

~    In the UK we use technologies that may not be used in your country. If they are not (and will never) be used in your country, then you can remove these.

As another country developing a calculator, what *outputs* should we be interested in?

~    We look at emissions, costs, energy security (imports and exports, energy mix), air quality and are considering water and biodiversity impacts. Which of these are important for you? (If they are not needed, it's worth removing them to make the model more simple) What have we missed?

What kind of team structure works best for building an Excel model? How many people are needed, and what kind of roles & experience are most important.

~    For the sector work, it's really helpful to have a range of different experiences on the relevant sectors.  We strongly recommend having someone in a Central Coordination role, and it's very helpful for them to have Excel expertise so that they can take charge of merging the Excel spreadsheet.

As a team working on the Excel model, what should we think about when the team is restructured?

~    From our experience with other teams it can cause delays when a team is restructured. The most important considerations are:  -the overall time given to the project: can the new team devote as much time to the project as is needed. Are there any milestones which are likely to be missed, and how can you plan work to get back on schedule?  -training: it's important to give time for any new people to learn about the 2050 calculator and the parts relevant to their sector. We recommend new people read the 2050 book and this set of Frequently Asked Questions. The 2050 team would also be happy to help new people, either with a training session or by reviewing their work in more detail.

How could we represent cogeneration in our model?

~    To take answer from training slides

Should we treat the whole of Mexico as a single unit, or divide by north/South  Given that Mexico is already divided by electricity tariff, would it make sense for buildings sector to be divided?

~    Have you got a standard answer/one-pager for this?

What population figures have you used and how do you change them?

~    The population projections used in the UK's Calculator are central projections sourced from the Office for National Statistics, and are given in a ‘Table’ called “Global.Assumptions” in the “Global assumptions” worksheet. The figures in this ‘Table’ can be edited if the user wants to use different population assumptions.   Other countries have used sources from their own countries, but we always recommend using this as Global Assumptions.

What GDP growth rate assumptions have you used and how do you change them?

~    For the UK, GDP growth is assumed to be 2.0% in each year from 2007 to 2050, based on HM Treasury’s view of long-term growth in the UK. This assumption can be changed by altering the “GDP (2005 £m)” column in the “Global.Assumptions” ‘Table’, in the “Global assumptions” worksheet.   We recommend that you choose a GDP which seems sensible over the long-term, even if this might be slightly lower than recent trends. You may want to discuss this with stakeholders early in the process of building your model. You may also want to compare your assumptions on levers such as industry growth, to make sure these are consistent with your GDP assumption.

Does each lever correspond to a sector/sheet within the spreadsheet?

~    The list of levers doesn't directly correspond to the list of sectors.  Some sectors have no lever (e.g. unabated thermal generation). Whereas some sectors have more than one lever (e.g. the heat sector which has four)  Levers represent the complete list of main actions to target emissions: they control the main drivers for each sector.  (RC add details of how to find it)

## Transport

Do we still need to include new vehicles in 2010, given that this is before the base year?

~    If you are including costs in your calculator, the cost of cars in this year will be part of the total, so you will need to have a value for it. If no historic data is avaialble, you could just extrapolate based on trends before and afterwards.  If your calculator's version does not yet include costs, it is not essential to give this figure, but it would still be good practice in case costs are added in the future.

In case of international shipping could we use the sheet XII. e to model emissions from cross-border waterways (rivers) (Hungary does not have sea shore but there is international shipping on Danube river through or into Hungary)

~    Yes, if you can agree a method on how to apportion emissions and have data to estimate travel demand

Regarding aviation how are the international flights taken into account? What ratio of an arrival or departure flight is considered as local emission? (XII. c sheet)

~    For the purpose of this 2050 analysis, international aviation emissions have been assigned to the UK on the basis of all flights departing from the UK

The petrol and diesel demand is determined on transport sheets. Why is it necessary to deliver the oil product demand on sheet XV a? Is the demand for refinery products not matched with the transport energy demand in the model?

~    Refinery demand is determined by the indigenous production of oil. This is a choice for the user. If there is excess demand for oil above this indigenous production (for example, from high transport demand) then the Calculator will “import” the oil.

Where are the emissions from H2 and electricity based transport allocated? (at transport or at electricity/H2 production)?

~    The emissions from the H2 production are captured in sheet VIII.a. The emissions from electricity for transport are in each of the respective sector worksheets for the technologies that produce electricity. The transports sector sheets capture the combustion emissions associated with vehicles that have internal combustion engines.

On XII. b sheet the equations seems like a little confused. Could you please explain the equations from row 32-43 (we do not see the connection between fuel use and distance) and rows 72-75? However, in our views the efficiencies (row 61 & 69) as defined on the sheet, could be delivered simply as the ratio of fuel use and distance – this equation is not provided, isn’t?

~    There is a full answer here:  http://2050-calculator-tool-wiki.decc.gov.uk/pages/131

Is the electricity need of transport matched with the electricity generation supply? Is the emission from EVs reflected by the electricity fuel mix?

~    See answer to question 8. The emissions from electricity for transport are in each of the respective sector worksheets for the technologies that produce electricity. The transport sector sheets capture the combustion emissions associated with vehicles that have internal combustion engines.

Why does fuel cell technology in motor vehicles use gas?

~    The adoption of fuel cell technology in vehicles in the 2050 Calculator is determined by the user of the Calculator as follows:   1.The user selects the absolute number of motor vehicles that will be driven up to 2050, using the “domestic transport behaviour” lever;   2.The user selects the proportion of vehicles they want to be electrified up to 2050, using the “shift to zero emission transport” lever; and   3.The user selects the technology they want electrified motor vehicles to adopt (hydrogen fuel cells or battery electric) in the “choice of car and van technology” lever.     The 2050 Calculator then “produces” enough hydrogen to provide the hydrogen demanded by hydrogen fuels cell vehicles (specified by the user in steps i to iii). This production requires gas and electricity in proportions that vary over time:   1.Hydrogen is produced either by “steam methane reforming” (SMR) using gaseous hydrocarbons or “distributed water electrolysis” (DWE) using electricity; and   2.the Calculator assumes that over time hydrogen will increasingly be produced by DWE, and so produced using electricity rather than gas (it is assumed that by 2050 100% of hydrogen will be produced by DWE).

## Units

Under the individual Supply sheets, the "Fixed assumptions" section also has an "Implications" subsection (e.g. rows 70-71 in II.a (Nuclear), or 53-54 under III.a.2 (Onshore wind)).  We notice that units there are somewhat misleading, sometimes quoting capacity and then giving actually energy values instead of power. How are these values actually entering the model?

~    In the case of nuclear the ‘implications’ section is used to state the illustrative size of power station considered: 3GW. The lever for this sector allows the user to specify capacity in GW, so the illustrative station size is used to work out the number of power stations this would entail. The cost estimates we have for this sector are also on a 3GW station basis, so it’s necessary to know the number of stations to work out the costs. Precisely the same approach is used in the onshore wind sector.   (The ‘trace dependents feature on the ‘formulas’ tab is really useful for seeing how these figures are used. )

How do I add my currency to the Conversions sheet?

~    The Conversions sheet is designed so that this should be very easy to do, and this summary should help you understand how the units work. (Also see question 90):  http://book.2050.org.uk/calculator-book/appendix-4-units.html    The easiest way to add a new currency unit is to follow these steps:  RC to write

About units conversion in the excel, my real question is: What is the unit of the fixed numbers in these formulas? For example:     = (Unit.GW)*0,6. What is the unit of 0.6?  =0,04*(1/Unit.TWh). What is the unit of 0,04 ?     I guess the unit of energy is TWh and the unit of power is GW.

~    On your units question, I think the explanation here might be the best way to describe it.  http://book.2050.org.uk/calculator-book/appendix-4-units.html     To give some more explanation, in the UK calculator we use TWh as the energy unit preference (see the Preferences sheet). However the reason we always multiply any values by (Unit.name of unit) is that this allows people to enter numbers in any unit they choose, while ensuring that numbers are still displayed in the preferred unit through the spreadsheet.    So to take your example:  • 0.6 doesn’t have a unit itself, but if you write it into the calculator as (Unit.GW)*0.6 then it will always be treated as 0.6GW, and the cell will show it as 0.6, because GW are the preferred units.  • However if you wrote it as (Unit.MW) *0.6, then the cell calculation would show it as 0.0006 instead (again because the preferred unit is GW).

How do you change the units?

~    The units of measurement are defined in the “Preference” worksheet. It is possible to change the energy, power, area and money units of measurement.  See this link for more information about units: http://book.2050.org.uk/calculator-book/appendix-4-units.html

## Year sheet

I've changed the year sheet for one of the years. What do I need to do to update all the other year sheets?

~    All the year sheets are designed to have the same structure. They are essentially identical, apart from the year which they represent.  Just changing the year displayed in the top left-hand corner of the worksheet (cell E2) will cause the formulae to update so that the entire year sheet will then show data for the newly entered year.    So once you have made changes to one year sheet, you can create all the other year sheets by:  1) deleting all year sheets, except the one you have just updated  2) copying (duplicating) your updated year sheet the required number of times. (You can do this by right-clicking on the sheet tab at the bottom of the page, clicking 'Move or Copy', selecting 'create a copy' then clicking OK)  3) then entering the required years (2010, 2015, … , 2050) in cell E2 of the corresponding sheets.     You can read more about year sheets here: http://book.2050.org.uk/calculator-book/appendix-1-the-excel-model-structure.html#year-sheets
