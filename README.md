<div align="center">

# 👋 Hi, I'm Augusto Salazar Montes

### Software Acceptance Test Engineer | Embedded Validation Specialist

<a href="mailto:augustosm85@gmail.com"><img src="https://img.shields.io/badge/Email-augustosm85%40gmail.com-red?style=flat&logo=gmail&logoColor=white"></a>
<a href="https://linkedin.com/in/augusto-salazar-montes"><img src="https://img.shields.io/badge/LinkedIn-augusto--salazar--montes-blue?style=flat&logo=linkedin&logoColor=white"></a>
<a href="#"><img src="https://img.shields.io/badge/Location-Quer%C3%A9taro%2C%20M%C3%A9xico-green?style=flat&logo=google-maps&logoColor=white"></a>
<a href="#"><img src="https://img.shields.io/badge/Languages-ES_(Native)_%7C_EN_(B2)_%7C_FR_(B1)-orange?style=flat&logo=googletranslate&logoColor=white"></a>

<br>

<a href="https://github.com/Thecesar85/Thecesar85/blob/main/Resume_Augusto_Salazar.pdf">
  <img src="https://img.shields.io/badge/%F0%9F%93%84_Download_Resume-PDF-blue?style=for-the-badge&logo=adobeacrobatreader&logoColor=white" alt="Download CV">
</a>

</div>

---

## 🧠 About Me

I'm a **Software Acceptance Test Engineer** with 4+ years of experience in embedded software validation, test automation, and system integration for the **automotive industry**. I design and execute black-box and white-box test campaigns, perform root cause analysis, and ensure quality compliance.

<table>
<tr>
<td width="50%">
  🧪 <b>Test & Validation</b><br>
  <sub>Python · LabVIEW Core 1&2 · TestStand<br>CANoe · CANalyzer · CAN/CAN-FD<br>HIL/Bench Setups · CAPL (learning)</sub>
</td>
<td width="50%">
  🔬 <b>Debugging & Tools</b><br>
  <sub>Oscilloscopes · Logic Analyzers · Multimeters<br>TRACE32 · iSystem · UDS (ISO 14229)<br>UART · I2C · SPI · LIN (basic)</sub>
</td>
</tr>
<tr>
<td>
  💻 <b>Programming & DevOps</b><br>
  <sub>Python · C · C++ · VHDL · SQL · MATLAB<br>Git · GitHub Actions · Docker · Jira<br>Linux (basic) · Embedded Systems</sub>
</td>
<td>
  🌐 <b>Languages</b><br>
  <sub>Spanish (Native)<br>English (B2 Proficient — EF SET)<br>French (B1 — TCF)</sub>
</td>
</tr>
</table>

---

## 👨‍💻 Sample Code

```python
# Automated KPI extractor from CANoe test logs
# Parses ASC log files, computes Test Yield, FPY, Defect Density
import pandas as pd
import re
from pathlib import Path

def parse_canoe_log(filepath: str) -> pd.DataFrame:
    """Extract signal data and test verdicts from CANoe ASC logs."""
    pattern = re.compile(
        r'(?P<timestamp>\d+\.\d+)\s+\d+\s+(?P<channel>\w+)\s+(?P<id>0x[0-9A-Fa-f]+)'
        r'\s+(?P<dlc>\d)\s+(?P<data>[0-9A-Fa-f ]+)'
    )
    frames = []
    for line in Path(filepath).read_text().splitlines():
        if m := pattern.match(line):
            frames.append(m.groupdict())
    df = pd.DataFrame(frames)
    df['timestamp'] = df['timestamp'].astype(float)
    return df

# Usage
log = parse_canoe_log("test_run_20260415.asc")
print(f"Frames captured: {len(log)} | Lost: {log['dlc'].astype(int).sum() - len(log)}")
```

---

## 📖 Currently Learning

- 🔌 **CAPL scripting** for advanced CANoe automation
- 🚗 **ADAS validation methodologies** (ISO 26262 awareness)
- 🐳 **Docker & CI/CD pipelines** for test automation
- 🤖 **AI-assisted testing** — integrating LLMs into test result analysis

---

## 💼 Experience

### 🏢 Application Engineer — *Seica, Inc.*  
`Oct 2022 – Jan 2026` | Querétaro, MX

- Designed and executed automated test campaigns for automotive ECUs using LabVIEW & TestStand
- Monitored CAN/CAN-FD communication between ECUs using CANoe & CANalyzer
- Developed Python scripts for automated KPI reporting (Test Yield, Defect Density, First Pass Yield)
- Performed root cause analysis using oscilloscopes, logic analyzers, and multimeters
- Managed SQL databases & Git repositories for end-to-end traceability
- Collaborated with international teams across Mexico, US, and Italy

`🛠️ Python · LabVIEW · TestStand · CANoe · CANalyzer · SQL · Git`

---

### 🏢 Applications Engineer — *AB Test Solutions*  
`Jul 2022 – Oct 2022` | Monterrey, MX

- Implemented data acquisition systems and LabVIEW automation frameworks for automotive manufacturing

`🛠️ LabVIEW · SQL · Data Acquisition`

---

### 🏢 Solution Junior Engineer — *Reckon Solution*  
`Jan 2021 – Apr 2022` | Guadalajara, MX

- Programmed industrial control interfaces (LabVIEW / TestStand); test plans and SQL database management

`🛠️ LabVIEW · TestStand · SQL · HMI`

---

### 🏢 FPGA Intern — *IM2NP*  
`Mar 2020 – Jun 2020` | Salon-de-Provence, France

- Designed FPGA (VHDL) particle detection hardware; low-level debugging and timing analysis

`🛠️ VHDL · FPGA · Xilinx`

---

## 🔥 Projects

### 🧪 Technical Projects

| Project | Description | Tech |
|---------|-------------|------|
| **KPI Automation Suite** | Python scripts (pandas, matplotlib, Tkinter) to auto-extract & visualize test logs → PDF reports | `Python` `pandas` `Tkinter` |
| **Injector Test System** | Full embedded system: STM32, custom PCB, C firmware, MOSFET power stage, optocoupler isolation | `STM32` `C` `PCB` |
| **PIC ISP Programmer** | Firmware updates via In-System Programming for PIC16F84A / PIC18F4550 / PIC18F2550 | `PIC` `C` |

### 🏗️ Open Source & GitHub Projects

<table>
<tr>
<td width="50%">

🏥 **[MediSync](https://github.com/Thecesar85/MediSync)**  
*Unified Emergency Response & Hospital Coordination Platform*

🛡️ **[ao-bounty-control](https://github.com/Thecesar85/ao-bounty-control)**  
*Private control room for bounty PRs, issues & payout readiness*

💱 **[StellarBounty](https://github.com/Thecesar85/StellarBounty)** — Stellar/Soroban bounty platform

⭐ **[StellarPulse](https://github.com/Thecesar85/StellarPulse)**  
*Decentralized prediction market on Stellar/Soroban — bet XLM, earn PULSE*

</td>
<td width="50%">

💬 **[fluxer](https://github.com/Thecesar85/fluxer)**  
*Open source IM & VoIP app built for friends, groups, and communities*

📊 **[mergework](https://github.com/Thecesar85/mergework)**  
*Open-source work ledger — contributors & AI agents earn MRWK*

🐛 **[bug-bounty-codex-743](https://github.com/Thecesar85/bug-bounty-codex-743)** — Bounty hunting toolkit

⚒️ **[solfoundry](https://github.com/Thecesar85/solfoundry)**  
*Autonomous AI Software Factory on Solana — multi-LLM review & reputation*

</td>
</tr>
</table>

<details>
<summary>📦 More repos (click to expand)</summary>
<br>

- 📧 **[mautic](https://github.com/Thecesar85/mautic)** — Open Source Marketing Automation (7.x branch)
- 🎬 **[MoneyPrinterTurbo](https://github.com/Thecesar85/MoneyPrinterTurbo)** — AI video generation
- 📦 **[registry](https://github.com/Thecesar85/registry)** — Coder modules & templates registry
- 💎 **[solidity](https://github.com/Thecesar85/solidity)** — Smart Contract Language
- 👁️ **[zeroeye](https://github.com/Thecesar85/zeroeye)** — Trade risk monitor & diagnostics
- 🏕️ **[TentOfTrials-bounty-67](https://github.com/Thecesar85/TentOfTrials-bounty-67)** — Trading & market platform
- 🐉 **[Mudlet](https://github.com/Thecesar85/Mudlet)** — MUD client with Lua scripting

</details>

---

## 🎓 Education

| Degree | Institution | Year |
|--------|-------------|------|
| **Mechatronics Engineering** | Universidad Tecnológica de Tecámac, MX | 2022 |
| **Lic. Automated Systems & Industrial Computing** | IUT d'Aix-Marseille, France | 2020 |

> 📝 Thesis: *Automated Control System for Electromechanical Assembly Lines*  
> 🇫🇷 MEXPROTEC scholarship | Focus: Industrial Networks, Embedded Systems, Automation

---

## 📜 Certifications

<p align="center">
  <img src="https://img.shields.io/badge/LabVIEW-Core%201%20%26%202-00B383?style=for-the-badge&logo=national-instruments&logoColor=white">
  <img src="https://img.shields.io/badge/Google%20Cloud-Networking%20%26%20Security-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white">
  <img src="https://img.shields.io/badge/EF%20SET-English%20B2%20Proficient-58CC02?style=for-the-badge&logo=duolingo&logoColor=white">
  <img src="https://img.shields.io/badge/Cisco-Networking%20Academy-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white">
  <img src="https://img.shields.io/badge/Programming-Microcontrollers%20Cert-FF6C2C?style=for-the-badge&logo=arduino&logoColor=white">
</p>

---

## 🏔️ Beyond Work

- 🔌 **DIY Electronics**: Custom PCB design, firmware for IoT devices (ESP32, STM32)
- 🤖 **Emerging Tech**: AI integration, blockchain fundamentals
- 🚴 **Outdoors**: Hiking, cycling

---

<div align="center">

  <i>"Every challenge is an opportunity to create."</i>

  <br><br>

  <a href="mailto:augustosm85@gmail.com">📧 augustosm85@gmail.com</a> &nbsp;·&nbsp;
  <a href="https://linkedin.com/in/augusto-salazar-montes">💼 LinkedIn</a> &nbsp;·&nbsp;
  <a href="https://github.com/Thecesar85/Thecesar85/blob/main/Resume_Augusto_Salazar.pdf">📄 Download CV</a>

  <br>
  <img src="https://komarev.com/ghpvc/?username=Thecesar85&color=0A2942&style=flat-square" alt="Profile views">

  <sub>Last update: August 2026 · Querétaro, México</sub>

</div>
