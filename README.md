# light_control_bluepr# Light Control (Advanced Motion & Brightness Blueprint)

[![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Blueprint-blue.svg)](https://www.home-assistant.io/blueprints/)

## 📋 Description

This Home Assistant blueprint provides an advanced automation for controlling lights based on:
- **Motion detection**
- **Ambient brightness levels**
- **Optional night mode** with custom brightness
- **Blocking entities** to prevent automatic on/off actions
- **Timeout-based** auto switch-off if no motion is detected
- **Smooth operation** with customizable defaults

---

## ✨ Features

- Turn lights on when motion is detected and ambient brightness is below a threshold.
- Support night mode with reduced brightness at night.
- Auto turn-off lights after a defined delay with no detected motion.
- Support blocker entities to temporarily prevent switching on or off.
- Separate sets of lights for turning on and turning off.
- Smooth integration into any Home Assistant setup.

---

## 🛠️ Blueprint Details

| Property        | Value                             |
|:----------------|:----------------------------------|
| **Domain**      | `automation`                      |
| **Author**      | `sjuergen`                        |
| **Version**     | `1.0`                             |
| **Source URL**  | [GitHub Repository](https://github.com/your-repo/light-control-blueprint) |
| **Home Assistant** | Recommended 2023.5 or later    |

---

## ⚙️ Inputs

| Input | Description |
|:------|:------------|
| **Motion Sensor** | A binary sensor (device_class: motion) to detect motion. |
| **Brightness Sensor** | A sensor measuring ambient light (device_class: illuminance). |
| **Maximum Brightness** | If the ambient brightness exceeds this threshold (in lux), lights won't turn on. |
| **Auto-Off Delay** | Minutes to wait after no motion before turning off lights. |
| **Lights to Turn On** | List of lights to turn on when motion is detected. |
| **Additional Lights to Turn Off** | Additional lights to turn off after timeout. (Optional) |
| **Entities Blocking Auto-Off** | Entities that, when on, prevent the lights from being automatically turned off. |
| **Entities Blocking Auto-On** | Entities that, when on, prevent the lights from being automatically turned on. |
| **Night Mode Entity** | Entity that indicates when Night Mode is active (e.g., schedule, input_boolean, binary_sensor). (Optional) |
| **Brightness for Night Mode** | Brightness percentage (0-100%) for lights when Night Mode is active. |

---

## 🚀 How to Use

1. **Import the Blueprint**  
   Go to *Settings → Automations & Scenes → Blueprints → Import Blueprint* in Home Assistant.  
   Use this URL:  
   [https://github.com/your-repo/light-control-blueprint/blob/main/light_control.yaml](https://github.com/your-repo/light-control-blueprint/blob/main/light_control.yaml)

2. **Create a New Automation**
   - Select "Light Control (Advanced Motion & Brightness)" from the list.
   - Configure all required inputs like motion sensor, lights, brightness thresholds, etc.

3. **Save and Enable the Automation**

---

## 🌙 Night Mode Example

If you want your lights to dim during the night:
- Create an **Input Boolean** (`input_boolean.night_mode`) or a **Schedule Helper** (`schedule.night_mode`).
- Select this entity in "Night Mode Entity".
- Configure "Brightness for Night Mode" (e.g., 20%).

During Night Mode (`state: on`), lights will turn on with the specified dimmed brightness.

---

## 📈 Advanced Tips

- Add a `transition` field manually inside service calls if you want smooth fades (e.g., 2 seconds fade-in).
- Use different automations per room for tailored behavior.
- Combine with Home Assistant **Presence Detection** for even smarter control.
- Use multiple **blocking entities** like "Cinema Mode", "Party Mode", etc., to temporarily disable auto lighting.

---

## 🛠 Example Use Cases

- **Bathroom lights** only on when motion detected and low brightness.
- **Hallway lights** very dim at night.
- **Living room** lights not auto-off during movie time (when TV is on).

---

## 🤝 Contribution

Contributions, ideas, and improvements are welcome!  
Feel free to open an [Issue](https://github.com/your-repo/light-control-blueprint/issues) or create a [Pull Request](https://github.com/your-repo/light-control-blueprint/pulls).

---

## 📜 License

This project is licensed under the MIT License.  
Feel free to use, modify, and distribute.

---

**Created by `sjuergen` ❤️**
