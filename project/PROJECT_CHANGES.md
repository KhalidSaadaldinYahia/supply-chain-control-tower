# Supply Chain Control Tower — local review changes

- Preserved the explicit synthetic-data disclosure and the multi-fact star-schema design.
- Disabled dense category labels on the two scatter/bubble charts; exact names remain available through legends and tooltips, avoiding overlapping PDF labels.
- Kept the directly inspectable PBIP/PBIR/TMDL source tree rather than a nested binary archive.
- Updated the `DataFolder` parameter for this local review copy.

All 34,700 fact rows remain unchanged: 16,500 sales orders, 3,800 purchase orders, and 14,400 inventory snapshots. Dense tables remain interactive and scrollable in Power BI; a native PDF re-export should be checked for page readability.
