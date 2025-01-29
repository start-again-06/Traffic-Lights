# Traffic-Lights

🚦 Traffic Light Simulation 🏎️
📌 Overview
This project simulates a traffic light system that manages vehicles at an intersection using an event-driven queue system.

💡 Key Features:
✅ Dynamic traffic light control based on car arrivals
✅ Event-driven simulation using a priority queue
✅ Adjustable parameters for traffic flow modeling

📂 Workflow
1️⃣ Traffic Light Logic 🚦
The traffic light follows these rules:

🔴 Red Light: Cars accumulate in a queue.
🟢 Green Light: When a car arrives, a timer (Tc) starts. After 30s, the light turns green.
⏳ Passage Time: The green light lasts for Tp × waiting cars (10s per car) before switching back to red.
2️⃣ Event-Driven System 📆
The system uses three types of events:
🔹 CAR(t) → A car arrives at time t. If the light is red, it waits.
🔹 R2G(t) → The light turns Red → Green after Tc delay if a car is waiting.
🔹 G2R(t) → The light turns Green → Red after all waiting cars have passed.

3️⃣ Priority Queue Implementation 📊
A heap-based priority queue (EventQueue) efficiently manages events based on their execution time.

🔍 How It Works
1️⃣ Car Arrival (CAR event)

If the light is green, the car passes.
If the light is red, it queues up.
If it’s the first car in queue, a Red-to-Green (R2G) event is scheduled in Tc seconds.
2️⃣ Traffic Light Change (R2G event)

The light turns green.
A Green-to-Red (G2R) event is scheduled after Tp × waiting cars seconds.
3️⃣ Traffic Light Turns Red (G2R event)

The light turns red again after all cars pass.
🐞 Fixes & Improvements
✅ Implemented missing event actions for CAR, R2G, and G2R.
✅ Optimized event queue operations with heapq.
✅ Enhanced readability with docstrings and inline comments.

📊 Simulation Results
🚗 The system dynamically adjusts green light duration based on traffic demand.
⏳ Efficient processing ensures minimal wait times for cars.
📉 Reduces idle green time, optimizing intersection flow.

📜 License
🔓 MIT License – Free to use and modify!
