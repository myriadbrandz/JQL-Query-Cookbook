# JQL Query Cookbook

A collection of useful Jira Query Language (JQL) snippets.

---

## 🧭 Basic Filters

**All open issues**
```
status = Open
```

**Issues assigned to me**
```
assignee = currentUser()
```

---

## ⏱ SLA & Time-Based Queries

**Issues updated in the last 24 hours**
```
updated >= -1d
```

**Due within next 7 days**
```
due <= 7d
```

---

## 📂 Project & Components

**Issues in a specific project**
```
project = PROJECTKEY
```

**Filter by component**
```
component = "Backend"
```

---

## 🚦 Status Tracking

**Recently resolved issues**
```
status changed to Done AFTER -3d
```

**Stuck in transitions**
```
status IN ("In Progress") AND updated <= -5d
```

---

## 🐞 Bugs & Priorities

**High-priority bugs**
```
issuetype = Bug AND priority >= High
```

**Unassigned critical issues**
```
priority = Critical AND assignee IS EMPTY
```

---

## 🔍 Keyword Search

**Search by text**
```
text ~ "authentication"
```

---

## 🔗 Linked Issues

**Issues blocking others**
```
issueLinkType = "Blocks"
```

---

✍️ _Customize these snippets with your team’s project keys, components, and workflows._
