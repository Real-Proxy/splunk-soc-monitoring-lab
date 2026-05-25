# HTTP SPL Queries

---

# Total HTTP Requests

```spl
source="http.log.gz"
| stats count 
```

---

# Total 404 Errors

```spl
source="http.log.gz" status_code=404
| stats count 
```

---

# Unique Source IPs

```spl
source="http.log.gz"
| stats dc(src_ip) 
```

---

# POST Requests

```spl
source="http.log.gz" http_method=POST
| stats count 
```

---

# HTTP Status Code Distribution

```spl
source="http.log.gz"
| stats count by status_code
```

---

# Top Source IPs

```spl
source="http.log.gz"
| stats count by src_ip
| sort -count
| head 10
```

---

# Most Targeted Servers

```spl
source="http.log.gz"
| stats count by dest_ip
| sort -count
| head 10
```

---

# 404 Scanning Detection

```spl
source="http.log.gz" status_code=404
| stats count by src_ip
| sort -count
| head 10
```

---

# HTTP Method Distribution

```spl
source="http.log.gz"
| search http_method IN ("GET","POST","HEAD","PUT","DELETE","OPTIONS","TRACE")
| stats count by http_method
```

---

# Source to Destination Relationships

```spl
source="http.log.gz"
| stats count by src_ip dest_ip
| sort -count
```

---

# DirBuster Detection

```spl
source="http.log.gz" "DirBuster"
| stats count by src_ip
```

---

# Potential Scanning Activity

```spl
source="http.log.gz" status_code=404
| stats count values(http_method) as methods by src_ip
| where count > 50
| sort -count
```