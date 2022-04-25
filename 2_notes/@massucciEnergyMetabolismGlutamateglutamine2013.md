---
citation-template: v0.2.0
creation-date: "2022:04:21-11:33:09"
---

%% Preview Links ------------------------------------------------ %%
[[#_related|related]]

%% Note Body --------------------------------------------------- %%
# Energy metabolism and glutamate-glutamine cycle in the brain: A stoichiometric modeling perspective

### Meta
- [[Reference Citation Data#citekey|citekey]]: massucciEnergyMetabolismGlutamateglutamine2013
- [[Reference Citation Data#authors|authors]]: Francesco A. Massucci, Mauro DiNuzzo, Federico Giove, Bruno Maraviglia, Isaac Perez Castillo, Enzo Marinari, [[Andrea De Martino]]
- [[Reference Citation Data#year|year]]: [[2013]]
- [[Reference Citation Data#doi|doi]]: https://doi.org/10.1186/1752-0509-7-103

### Abstract:
**Background:** The energetics of cerebral activity critically relies on the functional and metabolic interactions between neurons and astrocytes. Important open questions include the relation between neuronal versus astrocytic energy demand, glucose uptake and intercellular lactate transfer, as well as their dependence on the level of activity. 

**Results:** We have developed a large-scale, constraint-based network model of the metabolic partnership between astrocytes and glutamatergic neurons that allows for a quantitative appraisal of the extent to which stoichiometry alone drives the energetics of the system. We find that the velocity of the glutamate-glutamine cycle ($V_{cyc}$) explains part of the uncoupling between glucose and oxygen utilization at increasing $V_{cyc}$ levels. Thus, we are able to characterize different activation states in terms of the tissue oxygen-glucose index (OGI). Calculations show that glucose is taken up and metabolized according to cellular energy requirements, and that partitioning of the sugar between different cell types is not significantly affected by $V_{cyc}$. Furthermore, both the direction and magnitude of the lactate shuttle between neurons and astrocytes turn out to depend on the relative cell glucose uptake while being roughly independent of $V_{cyc}$. 

**Conclusions:** These findings suggest that, in absence of *ad hoc* activity-related constraints on neuronal and astrocytic metabolism, the glutamate-glutamine cycle does not control the relative energy demand of neurons and astrocytes, and hence their glucose uptake and lactate exchange.


---

## Background
Sustained cerebral activity is crucially dependent on the functional and metabolic interplay of neurons and glial cells. Spectroscopic and imaging methods have indeed shown that the brain accommodates a wealth of cell-to-cell interactions, which ultimately have contributed to displace the decades-old notion that merely coupled whole brain activity to neuronal glucose oxidation (for a comprehensive review, see [[@mangiaMetabolicHemodynamicEvents2009|[1] ]]). In particular, carbohydrate metabolism is compartmentalized among neurons and astrocytes, which, together with the interstitial space, represent nearly 90$\%$ of the tissue. Although there is evidence for the trafficking of metabolic intermediates between the two cell types, its significance and dependence on the activation state are not fully elucidated. More than 15 years ago it was hypothesized that astrocytes may support the energetics of brain function by the provision of glucose derived lactate to neurons, in an activity-dependent manner [[@dienelAstrocyteActivationWorking2006|[2] ]]. However, the idea of a metabolically significant astrocyte-to-neuron lactate shuttle (ANLS), as well as the activity-dependent increase in astrocytic glucose uptake, has proven to be rather difficult to confirm in vivo, while indirect and not always reproducible experimental proof was mainly obtained from experiments on cell cultures (see [[@dienelAstrocyteActivationWorking2006|[3] ]], [[@bakGlucoseNecessaryMaintain2006|[4] ]] and the excellent reviews [[@dienelAstrocyticEnergeticsExcitatory2013|[5] ]], [[@mergenthalerSugarBrainRole2013|[6] ]]).

The difficult interpretation and integration of the experimental findings produced a substantial theoretical effort aimed at characterizing intra- and inter-cellular metabolic fluxes [[@aubertInteractionAstrocytesNeurons2005|[7] ]][[@aubertCoherentNeurobiologicalFramework2007|[8] ]][[@simpsonSupplyDemandCerebral2007|[9] ]][[@mangiaVivoNeurontoastrocyteLactate2009|[10] ]][[@dinuzzoChangesGlucoseUptake2010|[11] ]][[@somersaloMetabolismNeuronsAstrocytes2012|[12] ]]. So far, mathematical models of transport and metabolism of glucose in neurons and astrocytes using either kinetic [[@aubertInteractionAstrocytesNeurons2005|[7] ]][[@simpsonSupplyDemandCerebral2007|[9] ]][[@mangiaVivoNeurontoastrocyteLactate2009|[10] ]][[@dinuzzoChangesGlucoseUptake2010|[11] ]] or stoichiometry-based [[@calvettiDynamicActivationModel2011|[13] ]][[@jolivetDecipheringNeurongliaCompartmentalization2009|[14] ]][[@occhipintiAstrocytesGlucoseShunt2009|[15] ]] approaches have provided conflicting results about the relevance of the cell-to-cell lactate shuttle (CCLS) (see [[@dienelBrainLactateMetabolism2012|[16] ]] for a recent review). This, in turn, raised some debate, especially concerning the partitioning of glucose between neurons and astrocytes and the potentially resulting intercellular lactate flow [[@jolivetCommentRecentModeling2010|[17] ]]. A recent flux-balance-analysis (FBA) study indicates that the direction and magnitude of the CCLS between neurons and astrocytes depends critically on the relative uptake of blood-borne glucose [[@calvettiMenageTroisRole2012|[18] ]]. The sharing of glucose between the two cell types is itself governed by the internal energetic demand of cells, implying that glucose partitioning alone cannot be used to draw any conclusion on the functional variations of the CCLS [[@dinuzzoChangesGlucoseUptake2010|[11] ]]. A critical reassessment of previous modeling results suggests that the CCLS might remain of minor significance in terms of transferred carbon equivalents [[@sResponseCommentRecent2011|[19] ]].














On the other hand, the known regulations of enzymecatalyzed reactions implemented in dynamical models have so far proved insufficient to justify a fundamental energetic role for the CCLS [[@dinuzzoChangesGlucoseUptake2010|[11] ]]. In particular, the differences between metabolic pathways of neuronal and astrocytic networks do not imply the occurrence of lactate exchange between cells, most likely because neurons and astrocytes do possess a relatively high self-sufficiency for both glycolytic and oxidative glucose metabolism (see [20] and references therein). This means that lactate is oxidatively metabolized in the same compartment where it is produced by glycolytic processing of glucose.

The aim of this study is to examine the activitydependent metabolic cooperation of glutamatergic neurons and astrocytes from a network-based perspective. Specifically, two issues lie at the core of our work: (i) the correlation between partitioning of glucose and lactate shuttling; and (ii) their functional modulation across varying levels of glutamate-glutamine cycle. We have employed a constraint-based setting where an extensive and controlled sampling of the solution space is possible [21][22] on a large-scale model of compartmentalized brain energy metabolism. At odds with previous studies employing constraint-based schemes to analyze the neuron-glia system in specific conditions (different from those considered here, see [23]), our approach does not rely on an objective function (which in our case would be hard to design) to define the relevant states. In addition, it allows to analyze in detail the feasible metabolic states for networks whose sizes are beyond those covered by other approaches like Bayesian Flux Balance Analysis (BFBA) [[@occhipintiAstrocytesGlucoseShunt2009|[15] ]] or Montecarlo sampling of mass-balance equations [24]. Finally, we have not made any special assumption on the regulation of biochemical pathways with respect to the activation level, nor have we imposed specific constraints on transport fluxes (except for the uptake of glucose that we use to fine-tune the oxygen-to-glucose index (OGI), see below). In short, we show that, within our stoichiometric approach:

- (a) the OGI is able to distinguish states characterized by different levels of neurotransmission, as flux configurations with larger OGIs typically carry smaller values for the velocity of the glutamate-glutamine cycle; 
- (b) the partitioning of glucose between neurons and astrocytes is roughly independent of the level of activity; 
- (c) the magnitude and direction of the CCLS depend strongly on glucose partitioning while being roughly independent of the level of neurotransmission.

In other terms, within a purely stoichiometric model, the system’s energetics is determined to a significant extent by the sharing of glucose. These results support the idea that neurotransmission does not impose significant constraints on glucose partitioning or CCLS. In addition, we show that (d) the overall degree of correlation among metabolic reaction fluxes between and within cells changes drastically in the presence of neurotransmission, pointing to an extended metabolic and possibly functional partnership between neurons and astrocytes.

%% Reference
[1] -> [@mangiaMetabolicHemodynamicEvents2009]
%%












%% Extras ------------------------------------------------------- %%
#
___

###### _related: 
%% Add global links/note here %%
#DocType/ReferenceView #Stub #KeywordsMissing 
#Vault/MetBrain_md
#review/Research 
___