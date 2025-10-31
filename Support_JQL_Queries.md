# Support JQL Query Examples

A curated list of high-value Jira Query Language (JQL) searches commonly used for Support operations.

---

## 1️⃣ Tickets Assigned to Me

```
assignee = currentUser() AND status != Done ORDER BY priority DESC
```
Shows all open issues currently assigned to you, sorted by priority.  
✅ Use for daily triage dashboards.

---

## 2️⃣ Open Tickets by Priority

```
project = "Support" AND statusCategory != Done ORDER BY priority DESC
```
Lists all unresolved tickets in the Support project ranked by priority.  
✅ Useful for prioritization and workload balancing.

---

## 3️⃣ Tickets Breaching SLA Soon

```
project = "Support" AND "Time to resolution" <= remaining("1h") AND statusCategory != Done
```
Finds tickets that are close to violating SLA targets.  
✅ Perfect for proactive monitoring dashboards.

---

## 4️⃣ High-Priority Unassigned Tickets

```
priority in (Highest, High) AND assignee is EMPTY AND statusCategory != Done
```
Flags critical tickets that haven’t been assigned.  
✅ Helps prevent dropped or delayed cases.

---

## 5️⃣ Recently Created Tickets

```
project = "Support" AND created >= -1d ORDER BY created DESC
```
Displays tickets created in the last 24 hours.  
✅ Used for daily incident intake reports.

---

## 6️⃣ Tickets Reopened After Resolution

```
status changed TO Reopened AFTER -7d
```
Shows issues that were reopened within the last week.  
✅ Good for QA or identifying recurring problems.

---

## 7️⃣ Customer Tickets Waiting for Response

```
status = "Waiting for Support" AND updated <= -2h
```
Lists tickets awaiting agent response for more than two hours.  
✅ Improves customer success and response times.

---

## 8️⃣ Tickets Resolved This Week

```
project = "Support" AND resolutiondate >= startOfWeek()
```
Tracks all tickets resolved since the beginning of the week.  
✅ Great for performance metrics and reporting.

---

## 9️⃣ Frequent Reporter Check

```
reporter = currentUser() AND created >= -30d
```
Shows all tickets you (or a client) have logged in the last 30 days.  
✅ Useful for tracking repeat issues.

---

## 🔟 Linked Development Bugs

```
issueFunction in linkedIssuesOf("project = DEV AND status != Done", "Relates")
```
Pulls all support issues linked to unresolved bugs in the DEV project.  
✅ Enhances cross-team visibility between Support and Engineering.

---

✍️ _Customize project names, SLA fields, and workflow status for your Jira instance._
