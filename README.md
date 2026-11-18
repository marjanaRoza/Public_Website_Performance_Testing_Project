# ⚡ Website Performance Testing with Apache JMeter

Load test of a public website containing four pages using Apache JMeter: 100 concurrent virtual users, 800 requests in total, with response code and message assertions and an HTML dashboard report.

## 📌 Project Overview

This project measures how a website responds under concurrent load. It simulates 100 users browsing four pages and records response times, throughput, and error rate. Results are saved as a `.jtl` file and turned into a JMeter HTML dashboard.

## 🎯 Test Scenario

| Setting | Value |
|---------|-------|
| 👥 Virtual users (threads) | 100 |
| ⏱️ Ramp-up period | 2 seconds |
| 🔁 Loop count | 2 |
| 📨 Total requests | 800 (100 users × 2 loops × 4 pages) |
| 🌐 Protocol / Method | HTTPS / GET |

**Pages tested**

| # | Transaction | Target |
|---|-------------|--------|
| 1 | `Page_1_Home_Page` | `https://www.toolsqa.com/` |
| 2 | `Page_2_Selenium_Training` | `https://www.toolsqa.com/selenium-training?q=headers` |
| 3 | `Page_3_Playground` | `https://demoqa.com/` |
| 4 | `Page_4_About` | `https://www.toolsqa.com/about` |

## ✅ Assertions

Each request is checked with Response Assertions:

- Response code is **200**
- Response message is **OK**
- Request/response headers and body checks

## 📊 Test Execution Summary

| Metric | Result |
|--------|--------|
| Total Samples | 800 |
| Errors | 0 (0.00%) |
| Average Response Time | 2,974 ms |
| Median Response Time | 2,294 ms |
| Min / Max Response Time | 161 ms / 11,812 ms |
| 90th Percentile | 7,262 ms |
| 95th Percentile | 9,727 ms |
| 99th Percentile | 11,450 ms |
| Throughput | 31.5 requests/sec |
| Received / Sent | 1,471.9 KB/sec / 3.9 KB/sec |

**Observation:** all 800 requests succeeded with no errors, but response times varied widely under load. The average was about 3 seconds, and the slowest 10% of requests took over 7 seconds.

## 🛠️ Tools & Technologies

![JMeter](https://img.shields.io/badge/Apache_JMeter-D22128?style=for-the-badge&logo=apachejmeter&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)

**Listeners used:** View Results Tree · Summary Report · Aggregate Report · Aggregate Graph · Assertion Results · Graph Results · View Results in Table

## 📁 Project Files

- 📄 `Project_1.jmx` – JMeter test plan
- 📈 `Project_1.jtl` – Raw test results
- 📊 `index.html` – HTML dashboard report (open in a browser)
- 🧾 `statistics.json` – Summary statistics

## ▶️ How to Run

**Prerequisites:** [Java](https://www.java.com) (8 or newer) and [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi)

1. Open `Project_1.jmx` in JMeter (GUI) to view or edit the test plan.
2. Run it from the command line in non-GUI mode:

```bash
jmeter -n -t Project_1.jmx -l Project_1.jtl -e -o report
```

3. Open `report/index.html` in a browser to see the dashboard.

> The `report` folder must not exist or must be empty before running.

## 💡 Key Skills Demonstrated

- Performance / Load Testing
- Test Plan Design (Thread Groups, Controllers, HTTP Samplers)
- Response Assertions
- Test Result Analysis (response time, percentiles, throughput, error rate)
- JMeter HTML Dashboard Reporting
- Non-GUI Test Execution

## ⚠️ Note

This test was run for learning purposes against public practice websites. Please do not run it at high load against sites you do not own or have permission to test.
