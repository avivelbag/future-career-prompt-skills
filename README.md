# Future Career Prompt Skills

803 prompts for 100 jobs that are emerging now or plausible within the next 10 to 20 years, packaged as [Claude Agent Skills](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview). One research agent per role worked out what the job involves, grounded it in today's closest real equivalents (pilots, companies, standards, regulations), and wrote ready-to-use prompts.

Some of these roles already exist in small numbers. The later entries in each group are more speculative, and their prompts ask Claude to flag open questions where a field is still unsettled.

## Layout

- `skills/<role>/SKILL.md`: one skill per role, with its prompts and any cautions
- `data/NNN.json`: the raw prompts as JSON
- `site/index.html`: a searchable page with copy buttons (open it in a browser)

## Install

Copy the skills you want into `~/.claude/skills/` for Claude Code, or upload a skill folder as a zip in Claude.ai under Settings → Capabilities → Skills.

```bash
cp -r skills/ai-red-teamer ~/.claude/skills/
```

You can also paste a prompt straight into any chat. Fill in the `[BRACKETED]` parts first.

## Roles

### AI and automation

1. [AI agent supervisor](skills/ai-agent-supervisor/SKILL.md)
2. [AI trainer and evaluator](skills/ai-trainer-and-evaluator/SKILL.md)
3. [AI safety auditor](skills/ai-safety-auditor/SKILL.md)
4. [Model behavior designer](skills/model-behavior-designer/SKILL.md)
5. [AI red teamer](skills/ai-red-teamer/SKILL.md)
6. [Agent workflow architect](skills/agent-workflow-architect/SKILL.md)
7. [Synthetic data engineer](skills/synthetic-data-engineer/SKILL.md)
8. [AI ethics officer](skills/ai-ethics-officer/SKILL.md)
9. [Human-AI teaming coach](skills/human-ai-teaming-coach/SKILL.md)
10. [AI incident investigator](skills/ai-incident-investigator/SKILL.md)
11. [Deepfake forensic analyst](skills/deepfake-forensic-analyst/SKILL.md)
12. [Algorithm bias auditor](skills/algorithm-bias-auditor/SKILL.md)
13. [AI personality designer](skills/ai-personality-designer/SKILL.md)
14. [Machine-to-human explainer for regulated decisions](skills/machine-to-human-explainer-for-regulated-decisions/SKILL.md)
15. [AI liability insurance adjuster](skills/ai-liability-insurance-adjuster/SKILL.md)

### Robotics and autonomous systems

16. [Robot fleet manager](skills/robot-fleet-manager/SKILL.md)
17. [Humanoid robot technician](skills/humanoid-robot-technician/SKILL.md)
18. [Drone traffic controller](skills/drone-traffic-controller/SKILL.md)
19. [Autonomous vehicle remote operator](skills/autonomous-vehicle-remote-operator/SKILL.md)
20. [Robot teleoperation trainer](skills/robot-teleoperation-trainer/SKILL.md)
21. [Warehouse automation integrator](skills/warehouse-automation-integrator/SKILL.md)
22. [Agricultural robot operator](skills/agricultural-robot-operator/SKILL.md)
23. [Surgical robot coordinator](skills/surgical-robot-coordinator/SKILL.md)
24. [Home robot installer](skills/home-robot-installer/SKILL.md)
25. [Drone delivery dispatcher](skills/drone-delivery-dispatcher/SKILL.md)

### Energy and climate

26. [Grid battery storage technician](skills/grid-battery-storage-technician/SKILL.md)
27. [Fusion plant operator](skills/fusion-plant-operator/SKILL.md)
28. [Small modular reactor technician](skills/small-modular-reactor-technician/SKILL.md)
29. [Carbon removal plant operator](skills/carbon-removal-plant-operator/SKILL.md)
30. [Carbon accounting auditor](skills/carbon-accounting-auditor/SKILL.md)
31. [Green hydrogen technician](skills/green-hydrogen-technician/SKILL.md)
32. [Geothermal drilling engineer](skills/geothermal-drilling-engineer/SKILL.md)
33. [Climate adaptation planner](skills/climate-adaptation-planner/SKILL.md)
34. [Wildfire resilience specialist](skills/wildfire-resilience-specialist/SKILL.md)
35. [Heat pump retrofit specialist](skills/heat-pump-retrofit-specialist/SKILL.md)
36. [Managed retreat coordinator for coastal towns](skills/managed-retreat-coordinator-for-coastal-towns/SKILL.md)
37. [Solar geoengineering monitor](skills/solar-geoengineering-monitor/SKILL.md)
38. [Battery recycling engineer](skills/battery-recycling-engineer/SKILL.md)
39. [Vehicle-to-grid coordinator](skills/vehicle-to-grid-coordinator/SKILL.md)
40. [Climate risk underwriter](skills/climate-risk-underwriter/SKILL.md)

### Space

41. [Satellite servicing technician](skills/satellite-servicing-technician/SKILL.md)
42. [Orbital debris removal operator](skills/orbital-debris-removal-operator/SKILL.md)
43. [Space traffic controller](skills/space-traffic-controller/SKILL.md)
44. [Lunar construction engineer](skills/lunar-construction-engineer/SKILL.md)
45. [In-space manufacturing technician](skills/in-space-manufacturing-technician/SKILL.md)
46. [Asteroid prospecting geologist](skills/asteroid-prospecting-geologist/SKILL.md)
47. [Space resource lawyer](skills/space-resource-lawyer/SKILL.md)
48. [Commercial space station crew member](skills/commercial-space-station-crew-member/SKILL.md)
49. [Spaceport operations manager](skills/spaceport-operations-manager/SKILL.md)
50. [Space tourism guide](skills/space-tourism-guide/SKILL.md)
51. [Lunar habitat life support technician](skills/lunar-habitat-life-support-technician/SKILL.md)
52. [Propellant depot operator](skills/propellant-depot-operator/SKILL.md)

### Biotech and health

53. [Gene therapy nurse](skills/gene-therapy-nurse/SKILL.md)
54. [Longevity clinician](skills/longevity-clinician/SKILL.md)
55. [Personalized medicine pharmacist](skills/personalized-medicine-pharmacist/SKILL.md)
56. [Microbiome therapist](skills/microbiome-therapist/SKILL.md)
57. [Organ bioprinting technician](skills/organ-bioprinting-technician/SKILL.md)
58. [Brain-computer interface technician](skills/brain-computer-interface-technician/SKILL.md)
59. [Neural implant rehabilitation therapist](skills/neural-implant-rehabilitation-therapist/SKILL.md)
60. [Synthetic biology designer](skills/synthetic-biology-designer/SKILL.md)
61. [Biosecurity screening officer](skills/biosecurity-screening-officer/SKILL.md)
62. [Cultivated meat production technician](skills/cultivated-meat-production-technician/SKILL.md)
63. [Telesurgery specialist](skills/telesurgery-specialist/SKILL.md)
64. [Digital therapeutics prescriber](skills/digital-therapeutics-prescriber/SKILL.md)
65. [Genetic counselor for embryo screening](skills/genetic-counselor-for-embryo-screening/SKILL.md)
66. [Exoskeleton fitter for mobility patients](skills/exoskeleton-fitter-for-mobility-patients/SKILL.md)
67. [Pandemic early warning analyst](skills/pandemic-early-warning-analyst/SKILL.md)

### Computing and security

68. [Quantum algorithm developer](skills/quantum-algorithm-developer/SKILL.md)
69. [Quantum hardware technician](skills/quantum-hardware-technician/SKILL.md)
70. [Post-quantum cryptography migration engineer](skills/post-quantum-cryptography-migration-engineer/SKILL.md)
71. [Digital identity verifier](skills/digital-identity-verifier/SKILL.md)
72. [Personal data broker](skills/personal-data-broker/SKILL.md)
73. [Privacy engineer](skills/privacy-engineer/SKILL.md)
74. [Smart contract auditor](skills/smart-contract-auditor/SKILL.md)
75. [Edge computing technician](skills/edge-computing-technician/SKILL.md)
76. [Neuromorphic chip designer](skills/neuromorphic-chip-designer/SKILL.md)
77. [Digital estate executor](skills/digital-estate-executor/SKILL.md)

### Immersive media and design

78. [Spatial computing designer](skills/spatial-computing-designer/SKILL.md)
79. [Virtual world builder](skills/virtual-world-builder/SKILL.md)
80. [Digital twin engineer](skills/digital-twin-engineer/SKILL.md)
81. [Virtual production stage operator](skills/virtual-production-stage-operator/SKILL.md)
82. [Synthetic performer director](skills/synthetic-performer-director/SKILL.md)
83. [Haptic experience designer](skills/haptic-experience-designer/SKILL.md)
84. [AI-assisted game master](skills/ai-assisted-game-master/SKILL.md)
85. [Digital fashion designer](skills/digital-fashion-designer/SKILL.md)
86. [Authenticity certifier for human-made media](skills/authenticity-certifier-for-human-made-media/SKILL.md)
87. [Memory archivist for personal digital histories](skills/memory-archivist-for-personal-digital-histories/SKILL.md)

### Food, cities, and manufacturing

88. [Vertical farm manager](skills/vertical-farm-manager/SKILL.md)
89. [Precision fermentation operator](skills/precision-fermentation-operator/SKILL.md)
90. [Urban air mobility pilot](skills/urban-air-mobility-pilot/SKILL.md)
91. [Vertiport manager](skills/vertiport-manager/SKILL.md)
92. [Smart city systems operator](skills/smart-city-systems-operator/SKILL.md)
93. [3D-printed construction technician](skills/3d-printed-construction-technician/SKILL.md)
94. [Modular housing assembler](skills/modular-housing-assembler/SKILL.md)
95. [Circular economy materials manager](skills/circular-economy-materials-manager/SKILL.md)
96. [Semiconductor fab technician for reshored plants](skills/semiconductor-fab-technician-for-reshored-plants/SKILL.md)

### Human-centered roles

97. [Reskilling coach for displaced workers](skills/reskilling-coach-for-displaced-workers/SKILL.md)
98. [Digital detox therapist](skills/digital-detox-therapist/SKILL.md)
99. [Elder care technology coordinator](skills/elder-care-technology-coordinator/SKILL.md)
100. [AI tutor supervisor for classrooms](skills/ai-tutor-supervisor-for-classrooms/SKILL.md)

## Caveat

These prompts are drafting aids written by AI agents. Standards, regulations and products named in them change quickly, so check them against current sources. Never paste confidential or personal data into a tool your organization hasn't approved.
