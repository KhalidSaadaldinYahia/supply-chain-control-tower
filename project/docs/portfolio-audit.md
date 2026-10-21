# Portfolio Design Audit — Working Notes

The five supplied PBIP packages were treated as representative builds, not necessarily final releases.

## Recurring strengths
- Clear analytical questions and methodology pages.
- Strong public-interest storytelling and explicit limitations.
- Consistent use of PBIP/PBIR/TMDL packaging.
- Increasing use of custom visual language and decision-support framing.

## Recurring constraints observed
- Beyond Wealth, Displacement Pulse, and Retail Pulse repeatedly use a four-card KPI row plus two main analytical panels.
- Most semantic models are a single flat imported table; Humanitarian Funding Triage also contains auto-generated local date tables.
- Several builds inherit visual/layout conventions from earlier projects, which makes the portfolio feel more templated than it needs to.
- Some review packages contain signs of copy-forward metadata/measure naming, reinforcing the need for stronger model QA before publication.

## Design response in this project
- Multi-fact star schema with conformed dimensions.
- Dedicated `_Measures` layer and explicit Date dimension; auto date/time disabled.
- Exception-first executive page instead of a generic summary grid.
- Different information architecture by page: exception queue, inventory positioning map, supplier risk map, fulfillment trend, and wide customer-exposure table.
- Commercial operations domain to broaden the portfolio beyond humanitarian/public-sector analytics.
