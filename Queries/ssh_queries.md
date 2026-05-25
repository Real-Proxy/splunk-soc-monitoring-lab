# SSH SPL Queries

---

# Total SSH Events

```spl
source="ssh.log.gz"
| stats count 
```

---

# Failed Login Detection

```spl
source="ssh.log.gz" status=failure
| stats count 
```

---

# Successful Login Detection

```spl
source="ssh.log.gz" status=success
| stats count 
```

---

# Unique Source IPs

```spl
source="ssh.log.gz"
| stats dc(src_ip) 
```

---

# Success vs Failure Analysis

```spl
source="ssh.log.gz"
| stats count by status
```

---

# Top SSH Attack Sources

```spl
source="ssh.log.gz" status=failure
| stats count by src_ip
| sort -count
| head 10
```

---

# Most Targeted Servers

```spl
source="ssh.log.gz"
| stats count by dest_ip
| sort -count
| head 10
```

---

# Source to Destination Relationships

```spl
source="ssh.log.gz"
| stats count by src_ip dest_ip
| sort -count
```

---
