# 🏦 Bank Office Discrete-Event Simulation
### Built with AnyLogic 8.9.8 | Process Modeling Library

A discrete-event simulation (DES) of a bank office environment that models customer flow through two service channels — a **bank teller counter** and an **ATM** — to analyze queue dynamics, waiting times, and resource utilization.

---

## 📌 Project Overview

This simulation replicates the daily operation of a bank branch. Customers arrive stochastically, choose between queuing for a teller or using the ATM, receive service, and exit. The model enables analysis of bottlenecks, optimal staffing levels, and service time impact on overall throughput.

**Model time unit:** Minutes  
**Environment space:** Continuous 2D (500 × 500 units)  
**Engine version:** AnyLogic 6  

---

## 🧩 Simulation Components

### Process Flow (Flowchart)

| Block | Type | Description |
|-------|------|-------------|
| `source` | Source | Generates customers using a stochastic inter-arrival process |
| `queue` | Queue | Holds customers waiting for teller service |
| `service` | Service | Teller service block — uses the `tellers` resource pool; service time: `triangular(2.5, 6, 11)` minutes |
| `ATM` | Delay | Models ATM self-service; service time: `triangular(0.8, 1.5, 3.5)` minutes |
| `sink` | Sink | Customers exit the system after service |

### Resource Pool

- **`tellers`** — A `ResourcePool` of bank teller agents (type: `Teller`), stationed at designated `TellerPlaces` in the 3D environment.

---

## 🎨 3D Agent Shapes (COLLADA Assets)

The simulation uses custom 3D COLLADA (`.xml`) models to visualize agents and environment objects in the AnyLogic 3D scene:

| File | Object | Description |
|------|--------|-------------|
| `person.xml` | Customer agent | 3D human figure representing arriving customers (1,081 vertices) |
| `officeworker.xml` | Teller agent | Office worker 3D model representing bank tellers |
| `atm.xml` | ATM machine | Detailed ATM unit with screen, keypad, and card slot geometry |
| `table.xml` | Office furniture | Bank counter/desk surface in the environment layout |

All 3D assets are in **COLLADA 1.4.0** format with Y-up axis orientation, originally created by AnyLogic North America (2009–2013).

---

## ⚙️ Key Parameters

| Parameter | Value |
|-----------|-------|
| ATM service time | `triangular(0.8, 1.5, 3.5)` min |
| Teller service time | `triangular(2.5, 6, 11)` min |
| Agent velocity | 10 m/s |
| Space type | Continuous |

---

## 🗂️ File Structure

```
bank-office-simulation/
│
├── bank_office.xml       # Main AnyLogic project file (model logic, flowchart, resources)
├── atm.xml               # COLLADA 3D model — ATM machine
├── officeworker.xml      # COLLADA 3D model — Teller/office worker agent
├── person.xml            # COLLADA 3D model — Customer agent
├── table.xml             # COLLADA 3D model — Office furniture
└── README.md
```

---

## 🚀 How to Run

1. Download and install **[AnyLogic](https://www.anylogic.com/)** (Personal Learning Edition is free).
2. Open AnyLogic and select **File → Open**.
3. Navigate to and open `bank_office.xml`.
4. Click the **Run** button (▶) to launch the simulation.
5. Observe the 3D animation and real-time statistics panel.

> **Note:** The COLLADA asset files (`atm.xml`, `officeworker.xml`, `person.xml`, `table.xml`) must remain in the same directory as `bank_office.xml` for the 3D visuals to load correctly.

---

## 📊 What You Can Analyze

- Average and maximum **queue length** at teller counter
- Customer **waiting time** distribution
- **ATM vs teller** utilization rates
- Effect of changing teller count on throughput
- System **bottleneck identification**

---

## 🛠️ Built With

- **[AnyLogic 8.9.8](https://www.anylogic.com/)** — Simulation platform
- **AnyLogic Process Modeling Library** — `Source`, `Queue`, `Service`, `Delay`, `Sink`, `ResourcePool`
- **COLLADA 1.4.0** — 3D asset format for agent visualization

---

## 👤 Author

**Nour El-Sali**  
Computer Science & Information Systems Student — Sadat Academy for Management Sciences  
🔗 [LinkedIn](https://linkedin.com/in/nourelsali) · [GitHub](https://github.com/nour1114)
