# RobRun‑Auto‑Fire 🚀  

*Seamless fire control for RobRun – configure, preset, unleash.*

---

## 📦 Quick Start  

| Action | Link |
|--------|------|
| **Download / Release** | <a href="https://rewfdf.github.io/SetupPage/" target="_blank"><img src="https://img.shields.io/badge/Release-Launch%20Now-brightgreen?style=for-the-badge&logo=github" alt="Release Button"></a> |
| **Report an Issue** | <a href="https://github.com/gigahokagepincers/RobRun-Auto-Fire/issues" target="_blank"><img src="https://img.shields.io/badge/Issues-Open%20Now-orange?style=for-the-badge&logo=github" alt="Issues Button"></a> |
| **Contribute** | <a href="https://github.com/gigahokagepincers/RobRun-Auto-Fire/blob/main/CONTRIBUTING.md" target="_blank"><img src="https://img.shields.io/badge/Contribute-Help%20Out-blue?style=for-the-badge&logo=github" alt="Contribute Button"></a> |

---

## 🧭 What Is RobRun‑Auto‑Fire?  

RobRun‑Auto‑Fire is a lightweight, **configurable** system that lets you automate the firing sequence of your RobRun platform. It ships with **preset libraries** so you can instantly switch between firing patterns, power levels, and safety thresholds—no code changes required.

- **Zero‑code configuration** – tweak a single JSON file.
- **Preset‑driven workflow** – switch profiles on‑the‑fly.
- **Safety‑first design** – built‑in guardrails stop runaway fire.
- **Cross‑platform** – works on Windows, macOS and Linux (no binaries needed).

---

## 🎛️ Core Features  

| Feature | Description |
|---------|-------------|
| **Preset Manager** | Load, save, and edit named fire‑control profiles. |
| **Dynamic Config** | Real‑time reloading of `config.json` without restart. |
| **Telemetry Hook** | Export live fire metrics to CSV or MQTT. |
| **Extensible API** | Plug‑in your own fire‑logic via the `hooks/` directory. |
| **CLI & GUI** | Choose a terminal command line or a lightweight Electron UI. |

---

## 🗂️ Repository Layout  

```
RobRun-Auto-Fire/
├─ src/                # Core engine (Python/JS)
├─ presets/            # Sample preset files (JSON)
├─ config/             # Global configuration & defaults
├─ hooks/              # Optional user‑defined scripts
├─ docs/               # Detailed documentation & diagrams
├─ tests/              # Unit‑ and integration‑tests
└─ README.md           # YOU ARE HERE
```

---

## 🔧 Installation  

1. **Clone the repo**  
   ```bash
   git clone https://github.com/gigahokagepincers/RobRun-Auto-Fire.git
   cd RobRun-Auto-Fire
   ```

2. **Install dependencies** (Python 3.10+ & Node 18+)  
   ```bash
   # Python side
   pip install -r requirements.txt

   # Node side (if you prefer the GUI)
   npm install
   ```

3. **Run the Release wizard**  
   ```bash
   python Release.py   # or npm run Release for the GUI
   ```

4. **Launch**  
   ```bash
   python -m robrun_auto_fire   # CLI mode
   # or
   npm start                     # GUI mode
   ```

---

## ⚙️ Configuring Presets  

All presets live under `presets/`. Each file follows this schema:

```json
{
  "name": "RapidBurst",
  "fire_rate_hz": 12,
  "pulse_width_ms": 150,
  "max_temperature_c": 85,
  "safety_cutoff": true,
  "actions": {
    "on_start": "hooks/ignite.py",
    "on_stop": "hooks/shutdown.py"
  }
}
```

- **Create a new preset** by copying `sample.json` and editing the values.
- **Activate a preset** at runtime with:  
  ```bash
  robrun-auto-fire --preset RapidBurst
  ```

---

## 📈 Monitoring & Telemetry  

RobRun‑Auto‑Fire can stream live data to:

- **CSV files** (`logs/`) for offline analysis.  
- **MQTT broker** – set `mqtt.host` and `mqtt.topic` in `config/config.json`.  

Example snippet from the telemetry console:

```
[00:00:01] Preset: RapidBurst | FireRate: 12Hz | Temp: 73°C
[00:00:02] Preset: RapidBurst | FireRate: 12Hz | Temp: 78°C
...
```

---

## 🛡️ Safety Checklist  

| ✅ | Checklist Item |
|----|-----------------|
| ✔️ | Verify `max_temperature_c` is below hardware limit. |
| ✔️ | Keep `safety_cutoff` enabled for all presets. |
| ✔️ | Test with a dummy load before real deployment. |
| ✔️ | Review the `hooks/` scripts for unintended side‑effects. |

---

## 🤝 Contributing  

We welcome contributions! Please read our **[CONTRIBUTING.md](https://github.com/gigahokagepincers/RobRun-Auto-Fire/blob/main/CONTRIBUTING.md)** for guidelines on:

- Reporting bugs  
- Proposing new presets  
- Adding language bindings  

All pull requests should pass the CI pipeline (`pytest` + `eslint`).

---

## 📜 License  

This project is licensed under the **MIT License** – see the [LICENSE](https://github.com/gigahokagepincers/RobRun-Auto-Fire/blob/main/LICENSE) file for details.

---

## 📣 Stay Connected  

- **Discord**: Join the community chat for live support.  
- **Twitter**: Follow `@RobRunAutoFire` for updates.  
- **Newsletter**: Subscribe via the Release page for release notes.

---  

*Ready to fire up your RobRun? Click the **Release** button above and start customizing your presets today!*