# Supply Chain Control Tower

A Power BI operational intelligence project for monitoring fulfillment, inventory, supplier performance, and working-capital exposure across a synthetic multi-warehouse supply chain.

The report is designed as an exception-led control tower: executive KPIs surface service and financial exposure first, then dedicated analytical pages help isolate inventory, supplier, warehouse, and customer-level drivers.

![Supply Chain Control Tower design system](dashboard-design-preview.png)

## What the dashboard answers

- Where are service failures putting customer revenue at risk?
- Which products and warehouses are exposed to stockout pressure?
- Where is excess inventory tying up working capital?
- Which suppliers combine delivery delays, quality issues, and late purchase-order exposure?
- Which warehouses and customers are driving fulfillment risk?

## Dashboard pages

### Control Tower

Cross-functional monitoring of order OTIF, revenue at risk, inventory value, stockout positions, supplier OTIF, service trends, warehouse exposure, and the highest-priority SKU exceptions.

### Inventory Intelligence

A focused inventory workspace combining days of supply, ABC/XYZ segmentation, stockout exposure, inventory shortage value, excess capital, and a replenishment action queue.

### Supplier Performance

Supplier OTIF, average lead time, defect rate, late purchase-order value, a delay-versus-quality risk map, and supplier-level scorecards.

### Fulfillment & Logistics

Revenue, gross margin, order OTIF, revenue exposure, fulfillment trends, warehouse service performance, and customer-level service exposure.

### Architecture & Methodology

Metric definitions, semantic-model architecture, engineering decisions, refresh instructions, and interpretation guidance.

## Key portfolio figures

- **$54.61M** modeled revenue
- **81.62%** order OTIF
- **$8.79M** revenue at risk
- **77.82%** supplier OTIF
- **$7.92M** late purchase-order value
- **$983.74K** latest inventory value
- **58** SKUs with stockout risk in the latest snapshot

## Technical architecture

- Power BI Project (`.pbip`)
- PBIR enhanced report definitions
- TMDL semantic model
- Three fact tables: sales orders, purchase orders, and monthly inventory snapshots
- Conformed Date, Product, and Warehouse dimensions
- Dedicated `_Measures` table with grouped business measures
- Explicit Date dimension with auto date/time disabled
- Separate KPI display measures and detail-level financial formatting
- Reusable `DataFolder` Power Query parameter
- Custom report theme and registered background images

## Data model

The project uses a multi-fact star-schema design rather than a single flattened table.

```text
                         DimDate
                            │
             ┌──────────────┼──────────────┐
             │              │              │
             ▼              ▼              ▼
     FactSalesOrders  FactPurchaseOrders  FactInventoryMonthly
          │                 │                   │
          ├── DimProduct ───┼───────────────────┤
          ├── DimWarehouse ─┼───────────────────┤
          └── DimCustomer   └── DimSupplier

                    _Measures
```

## Data

The included dataset is synthetic and deterministic, covering **1 January 2024 through 31 December 2025**.

It contains:

- 731 dates
- 120 products
- 5 warehouses
- 20 suppliers
- 240 customers
- 16,500 sales-order records
- 3,800 purchase-order records
- 14,400 monthly inventory snapshot records

The data is intended for portfolio demonstration and reproducible analysis, not operational decision-making.

## Open the project

1. [Download the Power BI project archive](Supply_Chain_Control_Tower_Power_BI_Project.rar) and extract it.
2. Open `SupplyChainControlTower.pbip` in a recent version of Power BI Desktop.
3. Open **Transform data → Manage Parameters**.
4. Set `DataFolder` to the included extracted `data` folder.

Preview the completed dashboard: [open the PDF](Supply_Chain_Control_Tower_Dashboard.pdf).
5. Select **Close & Apply**, then refresh the model.

## Design and development

The report uses an executive command-center visual system with dedicated page compositions rather than repeating a single dashboard template. Financial measures retain full precision in tables and analytical visuals, while KPI cards use dedicated display measures for readable K/M presentation.

## Limitations

- All business data is synthetic and generated for portfolio demonstration.
- Thresholds such as stockout and excess-inventory rules are analytical assumptions created for this project, not universal supply-chain standards.
- Revenue-at-risk and working-capital metrics are descriptive decision-support constructs and should not be interpreted as forecasts.

## Author

**Khalid SaadAldin Yahia**  
Data Analyst · Power BI · Python · SQL · Excel
