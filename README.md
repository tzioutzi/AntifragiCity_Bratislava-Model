## Bratislava Multimodal Mobility DSS
Overview
The Bratislava Model is an agent-based Decision Support System pilot designed to study and optimise multimodal mobility in the constrained topology of the Danube's riverbanks under operational disturbances of bridge infrastructure. It is one of three pilot case studies developed within the AntifragiCity project as the empirical workhorse of Deliverable D3.4 — Mobility Triage Analysis DSS.
The model serves three integrated purposes:
1.	Capture the multimodal network of Bratislava — directed primary and secondary roads, tram lines, bus routes and a ferry network connecting the riverbanks — sourced from OpenStreetMap and geolocated using QGIS 3.40 for maximum accuracy .
2.	Integrate socioeconomic land-use data — static patches carry population density and the distribution of socioeconomic profiles drawn from an official 2019 report, with travellers whose income is below half the population average automatically classified as vulnerable .
3.	Test responses to bridge-closure disruptions ranging from a single critical bridge to simultaneous closure of all three Danube crossings, evaluating how redistribution of modal share and the insertion of temporary ferry services mitigate the loss of cross-river capacity .
________________________________________
Key Features

🌉 Topologically Constrained Multimodal Network
•	Five layered networks coexist in the model: primary roads, secondary roads, tram lines, bus routes, and a ferry network connecting the riverbanks that is accessible to all agents subject to operational availability 
•	Edges are modelled as directed links, and nodes as stationary agents for maximum accuracy in network traversal .
•	Each mode uses its own network: cars travel on the road network, buses on the bus network, trams on the tram network .

👥 Agent-Based Mobility
•	Cars, buses and trams are dynamic autonomous agents that navigate according to their specific mode .
•	Traveller agents carry a socioeconomic profile inherited from the origin patch; their income level is drawn from a normal distribution, and they are flagged as vulnerable when their income falls below half the population average .
•	Destinations are randomly allocated at intersections or at stops of the traveller's selected transport mode .

📊 Configurable Parameters & Scenarios
The end-user can define:
Parameter	Description
Modal split	User-defined share of population across car, bus, tram 

Maximum car speed	Sets the upper-bound for the car agent kinematics 

Acceleration & deceleration	Affect the overall throughput and efficiency 

Delays in modal selection	Simulates hesitation and information lags when commuters choose modes 

Bridge closure scenario	Closure of one, two, or all three Danube bridges 

Response selector	Do-nothing / ferries / ferries + MS3 / ferries + MS4 

🎯 Response Strategies
Two response families are available for investigation:
•	Modal-share redistribution (MS1–MS4): three pre-defined modal scenarios, MS1 = 65% car / 19% bus / 15% tram (current Bratislava prevalence from a 2019 report); MS2 = 50/29/30; MS3 = 40/30/30; MS4 is the ferry-MS3 composite, with MS5 (or further variants: 20% car / 30% bus / 50% tram) introduced under combined interventions .
•	Temporary ferry service: inserts a previously absent modal link between critical transport nodes on opposite riverbanks, effectively bypassing the disrupted bridges to mitigate localised congestion 

📈 Built-In KPI Dashboard
The model tracks system capacity through KPIs defined in Deliverable D2.3:
•	Throughput (M) — total trip ends.
•	Trip ends of the vulnerable population — equity-aware throughput metric.
•	Efficiency (S) — system performance.
•	Redundancy (R) — availability of alternative pathways.
•	Entropy (Q) — satisfaction/psychological stress.
•	Theil-T index — socioeconomic inequity measure.
Output snapshots reflect the first ten minutes following the onset of the perturbation or the implementation of a response strategy, enabling a predictive assessment under constrained response time .
________________________________________
Empirical Foundation
The model's static structure is grounded in real demographic and modal data:
•	Socioeconomic profiles and population density are drawn from official report 50, distributed normally across the patches .
•	The initial distribution of users among transport modes is determined by a 2019 official report 51 .
•	Three bridge typologies are modelled explicitly: the multi-lane SNP Bridge (cars + buses), the rail-exclusive Stary Bridge, and Apollo Bridge, each with its own functional profile and cross-river capacity .
________________________________________
Demo Pilots in Context
Dimension	Bratislava
Mobility function examined	Multimodal commute across the Danube's two riverbanks 

Modes in the model	Cars, buses, trams, ferries (road / bus / tram networks) 

Socioeconomic layer	Static patches with population density & income; vulnerability = income < ½·average 

Disruption typology	Closure of one, two, or all three Danube bridges 

Response strategies	Modal-share redistribution (MS1–MS4) + temporary ferry insertion 

KPI family	Throughput, Efficiency, Redundancy, Entropy, + Theil-T 

________________________________________
Sample Insights
The model uncovers an important quantitative trade-off between system efficiency and spatial equity 
•	Modal shift alone raises throughput by >13% for both general and vulnerable populations and reduces overall inefficiency under normal conditions .
•	SNP closure (cars + buses) hits vulnerable users hardest: trip ends for vulnerable groups drop by −13.18% vs. −7.10% for the general population under the SNP-only closure .
•	The Theil-T index widens by up to 18% when the largest serviceability gains (35–56% additional completed trips when ferry + modal shift are combined) are realised — the same intervention that boosts absolute efficiency also concentrates accessibility to corridors used by specific income cohorts .
•	Combined closure of all three bridges reaches a saturation point where the equity index stabilises: when connectivity is uniformly broken, all users are penalised equally regardless of income .
•	Ferries act as a topology reconfiguration, not a redistribution. Inserting the ferry modal link generates antifragile gains that pure redistribution cannot match — combining ferries + MS3 raises serviceability from 6% to 65% of disrupted baselines 
________________________________________
Citation
If you use this model in academic work, please cite the parent deliverable:
Tzioutziou, A., Tsami, M., Xenidis, Y., et al.. D3.4 Mobility Triage Analysis DSS. AntifragiCity Project, 2026. Section 5.3.2 — Bratislava.
________________________________________
References
1.	Source document: D3.4 Mobility Triage Analysis DSS — Section 5.3.2 Bratislava, including subsections 5.3.2.1 Model Development, 5.3.2.2 Definition of Parameters and Scenarios, and 5.3.2.3 Simulations' Results 
2.	OpenStreetMap — Source of primary/secondary roads, bus and tram networks.
