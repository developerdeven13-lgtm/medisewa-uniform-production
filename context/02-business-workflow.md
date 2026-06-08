# Business Workflow

This document defines the official operational workflow of Medisewa Pvt. Ltd.

All application logic, database design, APIs, permissions, dashboards, reports, and automation must follow the workflows defined in this document.

No workflow state may be added, removed, or renamed without updating this document.

---

# Core Principles

The system is built around the following principles:

1. Accountability
2. Traceability
3. Auditability
4. Inventory Ownership Control
5. Data Integrity

Every physical movement must be recorded.

Every movement must have a sender and receiver.

Every receiver must acknowledge what was actually received.

Every workflow transition must be traceable.

All business actions must be auditable.

---

# Business Model

Medisewa owns all materials and finished products until delivery to the customer.

Tailoring shops are production partners and may hold company-owned inventory.

Inventory ownership never transfers to tailoring shops.

Tailoring shops may:

* Receive Materials
* Consume Materials
* Return Materials
* Receive Production Assignments
* Perform Production
* Perform Alterations
* Perform Repairs
* Perform Replacements
* Perform Rework

---

# High-Level Workflow

Customer
↓
Order Creation
↓
Order Approval
↓
Production Planning
↓
Production Assignment
↓
Material Availability Verification
↓
(Material Request & Issue If Required)
↓
Tailoring Shop Acknowledgment
↓
Production
↓
Finished Goods Return
↓
Company Acknowledgment
↓
Quality Control
↓
Delivery Preparation
↓
Delivery
↓
Order Completion

Issues may be raised at any stage.

---

# Physical Transfer Principle

Every physical movement follows the same lifecycle.

Transfer Created
↓
Items Handed Over
↓
Pending Acknowledgment
↓
Acknowledged
OR
Partially Acknowledged
OR
Rejected

Applicable To:

* Material Issue
* Material Return
* Material Recall
* Production Assignment
* Finished Goods Return
* Service Jobs
* Customer Complaint Items
* Internal Transfers

---

# Order Workflow

## Order Statuses

Draft

Pending Approval

Approved

In Production

Ready For Delivery

Delivered

Cancelled

---

# Production Workflow

## Purpose

Manage manufacturing of customer orders.

---

## Production Statuses

Planned

Production created.

---

Assigned

Assigned to tailoring shop.

---

Ready For Production

Required materials available.

---

In Production

Work started.

---

Completed

Production work completed.

Awaiting return.

---

Returned

Finished goods returned.

Awaiting acknowledgment.

---

QC Pending

Awaiting inspection.

---

QC Passed

Approved.

---

QC Failed

Rejected.

Rework may be required.

---

Closed

Production completed successfully.

---

# Production Assignment Workflow

Production Created
↓
Assigned To Tailoring Shop
↓
Pending Tailoring Shop Acknowledgment
↓
Acknowledged
↓
Ready For Production
↓
In Production
↓
Completed
↓
Finished Goods Returned
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
QC Pending

---

# Material Request Workflow

Material Request Created
↓
Company Review
↓
Approved
↓
Material Issued
↓
Pending Tailoring Shop Acknowledgment
↓
Acknowledged
↓
Inventory Updated
↓
Closed

---

# Material Return Workflow

Material Return Created
↓
Materials Returned
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
Inventory Updated
↓
Closed

---

# Material Recall Workflow

Recall Created
↓
Tailoring Shop Notified
↓
Materials Prepared
↓
Materials Returned
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
Inventory Updated
↓
Closed

---

# Finished Goods Return Workflow

Completed Production
↓
Items Returned
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
QC Pending

---

# Quality Control Workflow

QC Pending
↓
Inspection

Pass
OR
Fail

Pass Flow

QC Passed
↓
Ready For Delivery

Fail Flow

QC Failed
↓
Rework Service Job Created
↓
Assigned To Tailoring Shop
↓
Pending Tailoring Shop Acknowledgment
↓
Acknowledged
↓
Rework Performed
↓
Returned To Company
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
QC Pending

---

# Customer Complaint Workflow

## Purpose

Manage post-delivery complaints and after-sales service.

Customer Complaint Created
↓
Affected Items Selected
↓
Issue Review
↓
Approved
↓
Customer Returns Items
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
Investigation
↓
Resolution Determined
↓
Service Job Created
↓
Assigned To Tailoring Shop
↓
Pending Tailoring Shop Acknowledgment
↓
Acknowledged
↓
Work Performed
↓
Returned To Company
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
Quality Verification
↓
Delivered To Customer
↓
Customer Confirmation
↓
Issue Closed

---

# Customer Complaint Categories

Wrong Size

Alteration Required

Stitching Defect

Fabric Defect

Wrong Product

Wrong Color

Missing Item

Quantity Shortage

Logo Error

Delivery Damage

Replacement Request

Refund Request

Other

---

# Service Job Workflow

## Purpose

Manage work performed after initial production.

Service Job Types:

* Alteration
* Repair
* Replacement
* QC Rework

Workflow

Created
↓
Assigned
↓
Pending Tailoring Shop Acknowledgment
↓
Acknowledged
↓
In Progress
↓
Completed
↓
Returned To Company
↓
Pending Company Acknowledgment
↓
Acknowledged
↓
Quality Verification
↓
Closed

---

# Acknowledgment Workflow

## Purpose

Verify custody transfer of physical items.

Acknowledgment Statuses

Pending

Awaiting verification.

---

Partially Acknowledged

Some items received.

Some missing or disputed.

---

Acknowledged

All expected items verified.

---

Rejected

Transfer rejected.

Issue must be created.

---

Cancelled

Transfer cancelled.

---

# Inventory Workflow

## Purpose

Track material ownership and movement.

Company Inventory
↓
Material Issue
↓
Tailoring Shop Inventory
↓
Material Consumption
↓
Production
↓
Finished Goods
↓
Finished Goods Return
↓
Delivery

---

# Inventory Reconciliation Workflow

Verification Requested
↓
Physical Count
↓
Count Submitted
↓
System Comparison

Match
OR
Mismatch

Mismatch
↓
Issue Created
↓
Investigation
↓
Approved Adjustment
↓
Inventory Updated

---

# Delivery Workflow

Ready For Delivery
↓
Delivery Scheduled
↓
Out For Delivery
↓
Delivered
↓
Completed

Failed Delivery

Out For Delivery
↓
Delivery Failed
↓
Issue Created
↓
Rescheduled

---

# Issue Management Workflow

Issues may originate from:

* Inventory
* Production
* Material Transfers
* Tailoring Shops
* QC
* Delivery
* Customer Complaints
* Service Jobs

---

# Issue Statuses

Open

Assigned

Investigating

Resolved

Closed

Rejected

---

# Automatic Issue Creation Rules

Issues must automatically be created when:

* Transfer acknowledgment rejected
* Quantity mismatch detected
* Material discrepancy detected
* Inventory reconciliation mismatch detected
* QC failed
* Delivery failed
* Customer complaint investigation requires action
* Customer rejects completed resolution

---

# User Accountability Rules

Every critical operation must record:

* User
* Timestamp
* Entity
* Previous State
* New State

Examples:

* Order Creation
* Order Approval
* Production Assignment
* Material Issue
* Material Return
* Material Recall
* Acknowledgment
* QC Actions
* Delivery Actions
* Service Job Actions
* Issue Actions

---

# Cross-Module Rules

## Production Rules

Production Assignment can be created only when:

* Order status is Approved

Production can move to Ready For Production only when:

* Tailoring shop assigned
* Required materials available

Production can move to In Production only when:

* Production status is Ready For Production

Production can move to Completed only when:

* Production work finished

Production can move to Returned only when:

* Finished goods physically returned

* Company acknowledgment completed

---

## Quality Control Rules

QC can start only when:

* Finished goods acknowledgment completed

QC Failed automatically creates:

* Rework Service Job

---

## Service Job Rules

Service Job can be created only from:

* Customer Complaint
* QC Failure
* Authorized Manual Request

Service Job cannot close until:

* Returned items acknowledged
* Quality verification completed

---

## Delivery Rules

Delivery can be scheduled only when:

* QC Passed

Delivery can be completed only when:

* Customer receives products

---

## Customer Complaint Rules

Complaint investigation cannot start until:

* Returned items acknowledged

Complaint cannot close until:

* Customer confirmation recorded

---

## Order Rules

Order moves to In Production when:

* At least one production enters In Production

Order moves to Ready For Delivery when:

* All production assignments pass QC

Order moves to Delivered when:

* Delivery completed

Order can be cancelled only when:

* No active production exists
  OR
* Authorized cancellation approved

---

# Data Integrity Rules

The system must prevent:

* Negative inventory
* Duplicate acknowledgments
* Duplicate assignments
* Delivery before QC
* QC before acknowledgment
* Production without assignment
* Material issue without approval
* Service Job without source record

All business rules must be enforced on the server.

Frontend validation alone is not sufficient.

---

# Audit Requirements

The following operations must generate audit logs:

* Order Creation
* Order Updates
* Production Actions
* Material Actions
* Inventory Adjustments
* Acknowledgments
* QC Actions
* Delivery Actions
* Service Job Actions
* Issue Actions
* Permission Changes

Audit logs must never be deleted.
