
# Performance (Load-Stress) Testing with JMeter

Performance testing suite for the Restful-Booker API. The project evaluates the system's stability, throughput, and breaking point under a high-volume user scenario using **Apache JMeter**.

The objective is to simulate a real-world scenario where **120,000 users** interact with the booking system over a **12-hour period**.

### Testing Scenarios
1. **Auth - Login**: Authenticate user and obtain token.
2. **Create Booking**: Generate a new booking with dynamic random data.
3. **Search Booking**: Retrieve the newly created booking details by ID.

- **BaseURL**: `https://restful-booker.herokuapp.com`
- **Timer**: Gaussian Random Timer
  - *Deviation*: 2000ms
  - *Constant Delay*: 500ms
* Thread Properties
```bash
> Loop count          = 1	
> Number of user:     = 120,000
> Time:               = 12 hours
                      = 10*60 hours
                      = 43,200 SECOND 
> Users per 1 SECOND  = (120,000/43,200)
                      = 2.778
```



---

## How to Run the Tests

### Prerequisites
* **Install**: JAVA JDK (LTS)
* **Install**: Apache JMeter 5.x
* **Command Line Execution**
To ensure clean reporting, delete any existing **Report** folder and **.jtl** log files before running:

## How to run!
(1) Clone this repository:
   ```bash
   git clone https://github.com/ehasan321/Load-Stress-Testing-with-JMeter.git
   cd Load-Stress-Testing-with-JMeter
   ```

(2) Run the JMeter test in CLI (Non-GUI) mode to optimize performance and generate the results file:

**For Load Test:**
```bash
   jmeter -n -t Booking_Load_Stress.jmx  -l /Report/Booking_load.jtl -e -o /Report/LoadTest
```

**For Stress Test:**
```bash
jmeter -n -t Booking_Load_Stress.jmx  -l /Report/Booking_stress.jtl -e -o /Report/StressTest
```

* -n: Run in non-GUI mode.
* -t: Path to the JMX source file.
* -l: Path to the JTL file to log sample results.
* -e -o: Generate an HTML report in the specified "Reports" folder.

(4) **View the Results:** navigate to the Reports directory and open index.html






## Summary & Statistics
### 1. JMeter html Report:
**1.1 Load Test**

![image2](https://drive.google.com/uc?export=view&id=1vP2-MvohkZq8lL4s7-F3jKt5EAQFx0fk)

**1.2 Stress Test**

### 2. Manual Tested Report
**2.1 Load Test**

![image1](https://drive.google.com/uc?export=view&id=1hzG-mVm-PuooN_4IGC1pWUc7l0IHiydk)

**2.2 Stress Test**




---

## This is what I have done in this project

* **Scripted End-to-End User Flow:** Developed a JMeter test plan covering Auth Login, Dynamic Booking Creation (using random data), and Search Booking.
* **Realistic Load Simulation:** Configured a **Gaussian Random Timer** to mimic real-world user behavior and "think time."
* **Incremental Load Testing:** Conducted a 3-step load test (1, 5, 9, 10 and 15-minute intervals) to validate server stability for 120,000 users.
* **Stress & Bottleneck Analysis:** Performed stress testing to identify the server's breaking point and maximum throughput capacity.
* **Automated Reporting:** Generated **HTML Dashboards** and structured **Excel reports** for performance metric analysis (Latency, Error Rate, and TPS).




---

## Contributing

Contributions are welcome! If you would like to help improve this project, please feel free to contribute, simply fork the repository, create a feature branch, and submit a pull request with your changes.

Author: _@HASAN_
