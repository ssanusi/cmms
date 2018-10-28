CMMS - Computerized maintenance management system
---

## CMMS modules Specs
A. Equipment Management
   - Equipment / Asset
     - Uniq ID
     - Procedures
     - Hierarchy (Parent-Child)
     - Priority (What fix first ?)
     - Auxiliary Equipment
     - Cost (Calc by WO. Useful for Machine Replacement Analysis - MRA)
     - Links ( attach CAD, Shematics, Pneumatics, Scanned Doc, Img)
       - able to call in WOs or POs
     - Safety And Compliance
     - Warranty (able to show under warranty in WO)
     - Condition Monitoring
     - Reports
       - Cost
       - Failure, Count
       - Hirarchy
       - Warranty
       - Availability (Time available during a specified period)
       - Special Tools
       - Meter Reading
       - Location
   - Labor
   - WO
   - Inventory
   - Purchasing
   - Equipment History via WOs
   - Spare Parts (Recommended Info)
   - Run Time (use to trigger PM)
   - Safety Procedures
   - PM Schedules

   ## Tables
   asset : main properties
   asset_type : type of asset
   asset_contact : contact of asset incase there is any ploblem
   asset_part : middle table of asset-inventory
   asset_depreciation : depreciation of asset
   asset_comment : kind of log
   asset_downtime : downtime log
   asset_meter : meter of asset use for pm trigger
   asset_service_log : service log

   -----------------------------------------------------------------------

B. Preventive Maintenance (PM)
   - Intro
     - Perfromed regularly based on Calendar Time or Run Time (see Equipment Management)
     - Generate WO
   - Procedures
     - Task Details, Parts, Tools, Labor
   - Priority
   - Frequency
     - Calendar Time (weekly, monthly, ..) or Run Time (Miles, Hours, ..), Seasonal (summer, snow, ..)
   - Parts
     - Parts required including qty
   - Labor
     - Enter Craft Categories (Mechanic, Electrician, ..) and estimated hours
   - Outside Contrator
     - Able to contract to outside Vendor
   - Links as (Equipment Module)
   - Functions*
     - Generate WOs on its frequency setting
     - Route-based PM, a list of activities or inspections on a number of different equipment
       that are done by craft ppl
   - Reports
     - list by period of time
     - labor including money spent
     - material spent
     - labor projection (Use to forcast labor by specificed period)
     - material projetion (Use to forcast material by specificed period)

   ## Tables
   - pm
   - pm_step
   - pm_dependency
   - pm_comment
   - pm_tool
   - pm_audit
   - pm_part
   - pm_meter
   - pm_safety
   - pm_downtime
   - pm_season
   - pm_labor
   - pm_asset
   - pm_doc

   -----------------------------------------------------------------------

C. Labor
   - Properties
     - Hourly Wage Rate, Accomodate Overtime
     - Categories
     - Shift / Vocation / Sick
     - Craft Code
   - Links - as Equipment Management
   - Reports
     - Overtime
     - Vacation
     - WOs, Hours by account number / employee ID / Calendar Period / Equipment
     - Productivity ( estimated and actual hours )

   -----------------------------------------------------------------------

D. Work Order System (WO) ***
   - Intro
     - stores all preventive and corrective plan
     - emergency and scheduled
     - able to request by another department
   - Priority ( use for scheduled aid )
   - Status ( Approval, Wait for Material .. )
   - Category ( PM, Emergency, Repair, Project ) * should be user defined
   - Failure Code ( Should be user defined )
   - Action Code
   - Labor
     - able to enter multiple crafts ppl
   - Material ( Upon completion or as material is withdrawn )
   - Material Cost
   - Labor Cost
     - Based on Time Spent by each craft
   - Outside Cost and Total estimated cost
   - Total Actual Cost
   - WO completion
     - can be closed by individual or bath that matchs key
   - Downtime
     - able to track both planned and unplaned downtime
     - Planned means equipment is scheduled to be available for maintenance work
     - Unplanned means equipment goes down unexpectedly
   - Report
     - WO parts shortage
     - Active WO
     - Overdue WO
     - WO Material requirement
     - WO Labor requirement
     - WO detail
     - Downtime summary
     - WO by account
     - Activities
     - Performance ( % complete in time )
     - Cost Summary
     - Labor Summary
     - Material Summary
     - Equipment History
     - Cost Variance
   - Planning / Scheduling
   - Backlog
   - Priority System and Backlog
     - RIF - Relative Importance Factor = Priority X Equipment Criticality
     - Plan and schedule WOs based on RIF

   ## Tables ##
   - workorder
   - wo_step
   - wo_labor
   - wo_sched_labor
   - wo_part
   - wo_comment
   - wo_semaphor
   - wo_attachment
   - wo_meter
   - wo_tool
   - wo_status_log
   - wo_safety
   - wo_doc
   - wo_generation

   - wo_planned_downtime
   - wo_planned_part
   - wo_planned_labor
   - wo_planned_tool

   ------------------------------------------------------------------------

E. Vendor
   - Report
     - Able to print Label
     - Contact Report
     - Cost Variance

   ------------------------------------------------------------------------

F. Inventory
   - User defined reorder points
   - Able to create POs to restock
   - Many model to calc ROP(reorder point) and EOQ(economic order quantity)
   - Item trasactions
   - Description
   - Subsitiute

    ## Tables
    - inventory : main properties
    - in_tran : inventory transaction
    - in_vendor : middle table of inventory-vendor
    - in_comment : inventory comment
    - in_type : type of inventory
    - in_doc : link to document
    - in_reserved : middle table of workorder-inventory
    - in_audit : middle table of users-inventory
    - in_location : location
    - in_trans_worksheet
    - in_stock : location and qty

----------------------------------------------
## Project Under Developement

---