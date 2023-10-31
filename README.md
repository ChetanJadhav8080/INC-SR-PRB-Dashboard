# INC-SR-PRB-Dashboard
Analysis dashboard which monitors tickets life cycle and helps business take smart decisions and improve efficiency.
The pbix file size is very big, hence I ahve attached screenshots of Important Tabs like KPI, Hourly Analysis, Pareto Analysis, Caller ID Analysis.
Some Important DAX CODES: 
**Total Tkts Resolved in <1HR** = CALCULATE([Total Resolved tickets],'PPA EI_ISP Summary'[TTR] in {"<=1HR"})
**SLA** = 
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Major Incident -Priority 1" && 'PPA EI_ISP Summary'[SLA Time diff]>15 && 'PPA EI_ISP Summary'[SLA Time diff]<60, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Major Incident -Priority 1" &&  'PPA EI_ISP Summary'[SLA Time diff]>60, "R:Breached",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Critical-Priority 2" && 'PPA EI_ISP Summary'[SLA Time diff]>120 &&  'PPA EI_ISP Summary'[SLA Time diff]<240, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Critical-Priority 2" && 'PPA EI_ISP Summary'[SLA Time diff]>240, "R:Breached",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "High-Priority 3" &&'PPA EI_ISP Summary'[SLA Time diff]>1140 && 'PPA EI_ISP Summary'[SLA Time diff]<1440, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "High-Priority 3" && 'PPA EI_ISP Summary'[SLA Time diff]>1440, "R:Breached",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Medium-Priority 4" &&  'PPA EI_ISP Summary'[SLA Time diff]>3420 && 'PPA EI_ISP Summary'[SLA Time diff]<4320, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Medium-Priority 4" && 'PPA EI_ISP Summary'[SLA Time diff]>4320, "R:Breached",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Low-Priority 5" &&  'PPA EI_ISP Summary'[SLA Time diff]>11520 && 'PPA EI_ISP Summary'[SLA Time diff]<14400, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket type] = "INC" && 'PPA EI_ISP Summary'[priority] = "Low-Priority 5" && 'PPA EI_ISP Summary'[SLA Time diff]>14400, "R:Breached",

if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 2" && 'PPA EI_ISP Summary'[SLA Time diff]>1140 && 'PPA EI_ISP Summary'[SLA Time diff] <1440, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 2" &&  'PPA EI_ISP Summary'[SLA Time diff] >1440, "R:Breached",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 3" && 'PPA EI_ISP Summary'[SLA Time diff]>3420 && 'PPA EI_ISP Summary'[SLA Time diff] <4320, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 3" && 'PPA EI_ISP Summary'[SLA Time diff] >4320, "R:Breached",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 4" && 'PPA EI_ISP Summary'[SLA Time diff]>5760 && 'PPA EI_ISP Summary'[SLA Time diff] <7200, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 4" && 'PPA EI_ISP Summary'[SLA Time diff] >7200, "R:Breached",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 5" && 'PPA EI_ISP Summary'[SLA Time diff]>11520 && 'PPA EI_ISP Summary'[SLA Time diff] <14400, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 5" && 'PPA EI_ISP Summary'[SLA Time diff] >14400, "R:Breached",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 6" && 'PPA EI_ISP Summary'[SLA Time diff]>23040 && 'PPA EI_ISP Summary'[SLA Time diff] <28800, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 6" && 'PPA EI_ISP Summary'[SLA Time diff] >28800, "R:Breached",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 7" && 'PPA EI_ISP Summary'[SLA Time diff]>34560 && 'PPA EI_ISP Summary'[SLA Time diff] <43200, "Y:At Risk",
if('PPA EI_ISP Summary'[Ticket Type] = "SR" && 'PPA EI_ISP Summary'[priority] = "Level 7" && 'PPA EI_ISP Summary'[SLA Time diff] >43200, "R:Breached","G:Not At Risk"))))))))))))
))))))))
))



