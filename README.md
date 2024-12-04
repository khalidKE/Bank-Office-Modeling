# **Bank Office Model Simulation**  

This repository contains resources, tutorials, and reference models for creating and simulating a bank office service system using AnyLogic's **Process Modeling Library**. The repository is intended for beginners and advanced users looking to learn discrete-event simulation and apply it to service systems like banks, airports, and more.

---

## **Contents**
1. **Home**  
   - Overview of the repository.  
   - Key features and tools used in the modeling process.

2. **Tutorials**  
   - Step-by-step guide to building a bank office model.  
   - References to pre-built models for comparison and troubleshooting.

3. **Bank Office Model**  
   - A detailed simulation of a bank department featuring:  
     - Automatic Teller Machines (ATMs) for quick cash withdrawals.  
     - Teller lines for complex transactions like bill payments.

4. **Complexity**  
   - **Grade Levels**:  
     - Beginner  
     - Intermediate  
     - Advanced  
     - Expert  

---

## **Modeling Approach**
- **Discrete-Event Simulation**  
   The model employs a discrete-event approach to simulate processes where events occur at specific points in time.

---

## **Features**
- **Process Modeling Library**  
   A comprehensive set of tools for building flexible and complex models.  

- **3D Resources**  
   Enhance the visual representation of the system with 3D elements.  

- **Bar Chart**  
   Display operational data, such as customer arrivals and service times.  

- **Time-in-System Histogram**  
   Visualize customer journey data, including time spent at ATMs and teller lines.  

---

## **What Can You Model?**
Using AnyLogic’s **Process Modeling Library**, you can simulate:  
- **Manufacturing Processes**: Detailed shop floor layouts for production optimization.  
- **Service Systems**: Simple to complex systems like banks and airports.  
- **Business Processes**: Activity-based costing for process efficiency.  
- **Logistics and Supply Chains**: Optimize supply chain operations.

---

## **Tutorial Overview**
This tutorial focuses on creating a **bank service system** that includes:  
1. **Automatic Teller Machines (ATMs)**  
   - Quick self-service options for cash withdrawals.  

2. **Teller Lines**  
   - For complex transactions, providing customers with personalized service without inconveniencing others.  

### **Phases of the Tutorial**
#### **Phase 1: Creating a Simple Model**  
- Learn to build a foundational bank service system.  
- Collect and analyze basic statistics for validation.

---

### **Phases of the Tutorial**
#### **Phase 1: Creating a Simple Model**  
- build a foundational bank service system.  
- Collect and analyze basic statistics for validation.

---

#### **Phase 2: Creating Model Animation**  
-  add animations for better visualization of the system flow.
- Key Steps:
Design visual elements for queues.
Add animations for ATMs.
Adjust layout and markers for customer paths.

---

#### **Phase 3: Adding Tellers**  
- add tellers to the system to handle specific customer requests. This involves using resources to model teller behavior.

### Modifying the Flowchart
1. **Create a Service Block**:
   - Drag the **Service** block from the **Process Modeling Library** to the **Main** diagram.
   - Set `Queue capacity` to **20**.
   - Set `Delay time` to `triangular(2.5, 6, 11)`.

2. **Adjust the Process Flowchart**:
   - Add a **SelectOutput** block to divide customer flow between ATMs and tellers.
   - Set the condition in the **SelectOutput** block to `randomTrue(0.5)` for equal distribution.

3. **Add a ResourcePool for Tellers**:
   - Drag a **ResourcePool** block to the diagram and name it **tellers**.
   - Set its `Capacity` to **4**.
   - Connect the **Service** block to the **ResourcePool** using `Seize` and `Release`.

---

### Adding Space Markup Shapes
1. **Queue Area**:
   - Draw a **Rectangular Node** for the waiting area and name it **waitingArea**.
   - Link it to the queue in the **Service** block properties.

2. **Customer and Teller Areas**:
   - Create **Rectangular Nodes** for customer and teller positions, naming them **customerPlaces** and **tellerPlaces**.
   - Add **attractors** for customer positions and teller spots.
   - Align all nodes and attractors to ensure proper placement.

---

### Adding 3D Objects
1. **Teller 3D Objects**:
   - Create a **Resource Type** named **Teller** with an **Office Worker** figure.
   - Configure the **ResourcePool** to use this type.

2. **Teller Tables**:
   - Drag **Table** objects from the **3D Objects Palette** to align with teller attractors.
   - Adjust the rotation and position for proper alignment.

---

#### **Phase 4: Creating a Simple Model**  
- collect utilization and time-related statistics using charts and blocks.

### Collecting Utilization Statistics
1. **Bar Chart for ATM Utilization**:
   - Drag a **Bar Chart** to the diagram.
   - Add a data item titled **ATM utilization** with the value `ATM.statsUtilization.mean()`.

2. **Bar Chart for Queue Length**:
   - Add another **Bar Chart** for **Queue length**.
   - Set the value to `queue.statsSize.mean()`.

---

### Collecting Customer Time Statistics
1. **Measure Customer Time in System**:
   - Place a **TimeMeasureStart** block at the entry point of the flowchart.
   - Place a **TimeMeasureEnd** block near the sink and name it **timeTotal**.
   - Link the **TimeMeasureStart** block to the **TimeMeasureEnd** block.

2. **Histogram for Time Distribution**:
   - Drag a **Histogram** to the diagram.
   - Add a data item titled **Time in system distribution** with the value `timeTotal.distribution`.

---

## **Reference Models**
If you encounter difficulties or wish to compare your progress:  
- Access pre-built reference models for each tutorial phase.  
- View and download source files directly from the **AnyLogic Cloud**.

https://anylogic.help/tutorials/bank-office/index.html
