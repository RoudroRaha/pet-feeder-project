# Pet Feeder Project

## Problem Statement
A local animal shelter needs a simple and low-cost pet feeder for cats and dogs.  
The feeder must:
- Dispense food on time  
- Monitor food consumption  
- Alert staff if problems occur  

---

## Features Required
- Programmable feeding schedule  
- Portion control dispensing  
- Consumption observation  
- Alerts for errors (no dispense, no consumption, low storage)  
- Low-cost sensor-based design  

---

## Assumptions
- Dispenses dry food only
- One type of pet food dispensed only  
- One feeder per pen  
- Uses enclosed (local) network for alerts  
- Simple memory for records  
- Food will not dispense if storage is low  

---

## Inputs
- Feeding times  
- Food amount per service
- Scheduled time of dispense  
- Time allowed for eating  
- Sensor signals (bowl weight, storage level, motor movement)  

## Outputs
- Motor turns to serve food  
- Buzzer alerts for local staff  
- Network alerts for admin staff  
- Feeding history log  

---

## Pseudocode
- Start  
- Check time → if matches feeding time, continue; else wait  
- Check food storage → if Low, send “Low Food” + “No Dispense” alerts → End  
- Check motor → if Not OK, send “No Dispense” alert → End  
- Dispense food  
- Measure bowl weight  
- Start eating timer  
- After timer, measure bowl weight again  
- If food not eaten, send “Not Eaten” alert  
- If food eaten, log data  
- End  

---

## Testing Scenarios
- **Pet eats as expected** → Food dispensed, eaten, logged  
- **Pet does not eat** → Food dispensed, not eaten, “Not Eaten” alert  
- **Food bin empty** → “Low Food” + “No Dispense” alerts, nothing dispensed  
- **Motor fault** → “No Dispense” alert, no food, no log  

---

## Discussion
- Flowchart decisions worked as expected (time > storage > motor > dispense > consumption check).  
- Scenario 3 shows dual alerts are possible (“Low Food” + “No Dispense”).  
- Motor failure causes no log, avoiding confusion.  
- Scenario 2 proves timer and sensors work correctly.  

---

## Refinements
- Retry dispensing up to 2 times before alerting staff  
- Dispense based on bowl weight to avoid over/under feed  
- Regular manual maintenance and sensor testing  

