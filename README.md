**Preventive Maintenance of Agitator Using IIoT, Edge Gateway, OPC UA, MQTT and ThingsBoard Cloud**

A condition-based preventive maintenance prototype for industrial top-entry agitators in process and pharmaceutical plants. It shows how machine-health data can travel from the plant floor to a cloud dashboard, where abnormal conditions are flagged before they become failures.

Architecture: sensors → Siemens PLC → OPC UA server → Node-RED (OPC UA client and edge gateway) → MQTT → ThingsBoard Cloud → dashboard and alarms. Seven parameters are monitored per agitator: vibration, bearing temperature, motor temperature, process pressure, speed, motor power and cumulative energy. Two reference units are modelled: a 140 L fermenter agitator (3.7 kW) and a 4.5 KL unit (45 kW).

**Features**
Node-RED flows reading seven OPC UA tags and publishing JSON telemetry over MQTT
Warning and critical alarm rules, with motor-power limits scaled to each motor's rating
ThingsBoard dashboard with live trends, gauges and an alarm log for both agitators
Read-only PLC access, so control logic is never affected

**Status:** 
Simulation-based prototype. A Prosys OPC UA Simulation Server stands in for the plant PLC, so all readings are simulated and alarm thresholds are desk estimates pending site verification. This is condition-based monitoring, not predictive maintenance, and not a completed plant implementation.

**Next steps:** 
Connect a live Siemens PLC, validate thresholds against OEM data, harden security (OPC UA policies, TLS), and add ML-based predictive maintenance once real operating history exists.

**Tech:** Node-RED · OPC UA · MQTT · ThingsBoard · Prosys OPC UA Simulation Server
