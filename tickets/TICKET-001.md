# TICKET-001: P2 - MFA SMS OTP Failure

**Priority:** P2-High
**Status:** Closed / Resolved
**Live GitHub Issue:** [ MFA SMS OTP not delivered](https://github.com/antariksh19/cogs-support-lab-tickets/issues/1)

## Original Issue Description
Customer reports 25 users in the finance branch are unable to receive SMS OTPs for gateway login. The issue began at 08:00 system time.

---

## Incident Lifecycle Audit Trail

### Comment 1: Triage & Investigation
**Internal Investigation Note:**
Reviewed the Kaleyra dashboard logs for the affected user batch. Identified bulk `REJECTED` status codes on outbound SMS delivery. Investigating potential carrier-level routing blocks.

### Comment 2: Escalation
**L2 Escalation Handover:**
* **Issue:** Suspected TRAI DND (Do Not Disturb) carrier-level block on our sender ID.
* **Impact:** 25 users cannot authenticate to the ZTNA gateway.
* **Action Required:** Routing to the Network team to engage the carrier and adjust DND routing flags for this specific tenant block.

### Comment 3: Post-Incident Resolution (PIR)
**Resolution Summary:**
Root cause confirmed as a TRAI DND violation on the sender ID. Carrier routing adjusted by the network team. Tested successfully with 3 affected users who confirmed receipt of OTPs. Moving ticket to Resolved status and closing the issue.
