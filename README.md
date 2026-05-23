# Smart Irrigation and Soil Monitoring System

An IoT-based smart irrigation system developed using ESP8266 for real-time monitoring and automated water management. The system continuously monitors soil moisture, water flow rate, and pH levels, and automatically controls irrigation using relay-based automation.

Sensor data and daily averages are transmitted to the ThingSpeak cloud platform for remote monitoring and analytics.

# Components Used

 ESP8266 NodeMCU 
 Soil Moisture Sensor 
 pH Sensor 
 Water Flow Sensor
 Relay Module
 Solenoidal valve
 Jumper Wires
 Power Supply

# System Architecture

## Hardware Architecture

  ESP8266 acts as the central processing and communication unit.
  Soil moisture sensor measures soil water content.
  pH sensor checks water/soil acidity level.
  Water flow sensor measures irrigation flow rate.
  Relay module controls the water pump.
  WiFi connectivity enables cloud communication with ThingSpeak.

## Software Architecture

  ESP8266 reads sensor data periodically.
  Smart logic determines irrigation requirements.
  Relay activates the pump only under safe conditions.
  Sensor readings are uploaded to ThingSpeak using HTTP requests.
  Daily average values are continuously calculated and updated.
  Non-stop monitoring runs in a continuous loop.

#  Working Principle

1. The ESP8266 connects to the WiFi network.

2. The soil moisture sensor continuously monitors soil condition.

3. The pH sensor measures the pH level of water/soil.

4. If soil moisture falls below the defined threshold:
   - The system checks whether the pH value is within the safe range.

5. If both conditions are satisfied:
   - The relay activates the water pump.
   - Irrigation begins automatically.

6. During irrigation:
   - The water flow sensor measures water flow rate.

7. Sensor readings and calculated daily averages are uploaded to ThingSpeak cloud using HTTP requests.

8. If the soil moisture becomes sufficient or pH becomes unsafe:
   - The relay turns OFF the pump automatically.

9. Daily averages are reset automatically after 24 hours.


# Smart Irrigation Logic

## Pump ON Conditions

- Soil moisture below threshold
- pH value between safe limits

## Pump OFF Conditions

- Soil sufficiently wet
- Unsafe pH value detected

This prevents:
- Overwatering
- Water wastage
- Irrigation using chemically unsafe water


# Data Transmission

The ESP8266 sends the following data to ThingSpeak:

| Field   | Data             |

| Field 1 | Soil Moisture    |
| Field 2 | pH Value         |
| Field 3 | Water Flow       |
| Field 4 | Average Moisture |
| Field 5 | Average pH       |
| Field 6 | Average Flow     |

# License

This project is developed for educational, research, and smart agriculture applications.
