# Observability

Ability to infer internal system state from external data

- 3 Pillars of Observability → Types of data you collect
- 4 Golden Signals → What you measure about system health

## 3 Pillars of Observability

### 1. 📊 Metrics (Numbers over time)

**What it is:**
Numerical data collected over time.

**Examples:**

- CPU usage (%)
- Request rate (requests/sec)
- Latency (response time)
- Error rate

**Why useful:**

- Fast to query
- Good for alerts (e.g., CPU > 90%)

### 2. 📜 Logs (Detailed event records)

**What it is:**
Text records of events happening in your system.

**Examples:**

- "User login failed"
- Error stack traces
- API request logs

**Why useful:**

- Deep debugging
- Shows exact events and errors

### 3. 🔗 Traces (Request journey)

**What it is:**
Tracks a request across multiple services.

**Example:**
User request → API Gateway → Auth Service → DB → Response

**Why useful:**

- Understand latency bottlenecks
- Debug distributed systems

---

## 4 Golden Signals of Monitoring

### 1. ⏱️ Latency (Response Time)

**What it is:**
Time taken to process a request.

**Example:**

- User clicks “Login”
- Server responds in 200ms → good
- Server responds in 5 seconds → bad

**Important detail:**

Measure both:

- Successful requests
- Failed requests (timeouts often hidden)

👉 **High latency = slow system**

### 2. 🚦 Traffic (Demand)

**What it is:**
How much demand your system is handling.

**Examples:**

- Requests per second (RPS)
- Number of users
- Network I/O

👉 **Helps answer:**

- “Is the system overloaded?”
- “Did traffic suddenly spike?”

### 3. ❌ Errors (Failure Rate)

**What it is:**
Rate of failed requests.

**Examples:**

- HTTP 500 errors
- Failed DB queries
- Timeout errors

**Formula:**

`Error Rate = Failed Requests / Total Requests`

👉 **Even small increases can mean serious issues**

### 4. 📦 Saturation (System Capacity)

**What it is:**
How “full” your system is.

**Examples:**

- CPU usage (%)
- Memory usage
- Disk I/O
- Thread pool usage

👉 **High saturation = system close to failure**
