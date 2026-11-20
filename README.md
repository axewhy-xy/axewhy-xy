<div align="center">

<img src="assets/banner.svg" width="100%" alt="Lau Xiang Yang: Software Engineer · Computer Vision · Machine Learning · Simulation. Computer Science @ DigiPen Institute of Technology Singapore" />

[![Email](https://img.shields.io/badge/Email-xiangyang.1a2%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:xiangyang.1a2@gmail.com)
![Location](https://img.shields.io/badge/Based_in-Singapore-EF3340?style=for-the-badge)


<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/axewhy-xy/axewhy-xy/output/pacman-contribution-graph-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/axewhy-xy/axewhy-xy/output/pacman-contribution-graph.svg" />
    <img alt="Pac-Man eating my GitHub contribution graph" src="https://raw.githubusercontent.com/axewhy-xy/axewhy-xy/output/pacman-contribution-graph.svg" />
  </picture>
</p>

</div>

<h3><img src="assets/headers/about-me.svg" height="48" alt="About me" /></h3>

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

```
class Lau Xiang Yang {
public:
    std::string role         = "Software Engineer";
    std::string builds       = "Computer Vision and Machine Learning";

    std::vector<std::string> projects = {
        "Formula 9: Autonomous Shuttle Fleet Training Simulator",
        "HDB Feature Detection for Wolbachia Release Planning",
        "Illegal Fishing Detection"
    };

    std::vector<std::string> interests = {
        "LLMs",
        "Computer Vision",
        "Machine Learning"
    };

private:
    std::vector<std::string> hobbies = {
        "Traveling",
        "Reading"
    };
};
```

I turn real-world images into useful data. My work sits where **computer vision**, **machine learning**
and **simulation** meet: I build detection datasets from scratch, train object detectors on them, and
engineer simulation software that prepares people to operate autonomous vehicles.

<h3><img src="assets/headers/at-a-glance.svg" height="48" alt="At a glance" /></h3>

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

- 🔭 **Now:** leading development of **Formula 9**, an autonomous-shuttle fleet training simulator, in a team of 8
- 🎓 **Education:** B.S. Computer Science in Interactive Media and Game Development, **DigiPen Singapore** (Class of 2028)
- 🔌 **Previously:** Diploma in Electronic & Computer Engineering, **Ngee Ann Polytechnic**
- 💼 **Experience:** computer-vision internships at the **National Environment Agency** and the **National Parks Board**

<h3><img src="assets/headers/featured-work.svg" height="48" alt="Featured work" /></h3>

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

### 🚐 Formula 9: Autonomous Shuttle Fleet Training Simulator

<sub><b>Team project (8 developers) &nbsp;·&nbsp; Technical Lead &nbsp;·&nbsp; 2026 &nbsp;·&nbsp; In progress</b></sub>

A training simulator in which operators run a fleet of autonomous shuttles on real Singapore streets,
handling incidents, detours and charging in real time. A **Unity** client talks to a multi-core
**Python / FastAPI** simulation backend through versioned, schema-validated contracts, and the whole
system ships as a one-click Windows build.

<table>
  <tr>
    <td align="center"><b>60+</b><br><sub>commits authored</sub></td>
    <td align="center"><b>20+</b><br><sub>teammate PRs reviewed &amp; merged</sub></td>
    <td align="center"><b>2 → 8</b><br><sub>real-time sessions with traffic</sub></td>
  </tr>
</table>

- **Leadership:** own the repository and its architecture; authored 60+ commits and 20 pull requests, and
  reviewed and merged 20+ pull requests from teammates
- **Multi-core backend:** moved live sessions into supervised worker processes behind a single-writer
  gateway, with load-based admission and crash failover; sessions with traffic that keep real time rose
  from **2 to 8**, measured with a scaling benchmark I wrote
- **Native traffic engine:** ported the traffic simulation to a **C++** module (via **nanobind**) with an
  automatic Python fallback, held step-for-step identical by parity tests that run on both engines
- **Live streaming:** replaced polling with schema-validated **WebSocket** streams for snapshots and
  traffic, with heartbeats, clear close reasons, and automatic fallback to HTTP polling and reconnect
- **Traffic simulation:** built backend-driven city traffic in which shuttles and background vehicles obey
  simulated signals, and through which breakdowns, collisions, closures and signal faults play out, with
  checkpoint-and-recover for live sessions
- **Incident training:** designed world events that track which shuttles each incident affects,
  independent per-shuttle decisions (detour, hold, escalate), and the decision cards, notifications and
  live-detour route planner that drive them
- **Real-world city data:** introduced an **OpenStreetMap**-backed road network and an **LTA**-sourced
  traffic importer, and am extending it with generated sidewalks, kerb ramps and a pedestrian walk
  network whose crossings follow the traffic signals
- **3D city and shipping:** rendered roads, live incidents and smoothed shuttle motion in the 3D city, and
  wrote the build that bundles the Unity player with a portable Python backend that every open client
  shares and that shuts down cleanly

**Stack:** `C#` `Unity` `Python` `FastAPI` `C++` `nanobind` `WebSockets` `SQLite` `MongoDB` `JSON Schema` `OpenStreetMap`

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

### 🏢 HDB Feature Detection for *Wolbachia* Release Planning

<sub><b>National Environment Agency (NEA) &nbsp;·&nbsp; Internship &nbsp;·&nbsp; Apr – Aug 2026</b></sub>

An end-to-end computer-vision pipeline that detects building features linked to mosquito breeding in
imagery of Singapore's HDB blocks, helping researchers plan *Wolbachia-Aedes* mosquito releases.

<table>
  <tr>
    <td align="center"><b>~13.7k</b><br><sub>labelled images</sub></td>
    <td align="center"><b>~80k</b><br><sub>bounding boxes</sub></td>
    <td align="center"><b>5</b><br><sub>feature classes</sub></td>
    <td align="center"><b>2</b><br><sub>imagery sources</sub></td>
  </tr>
</table>

- **Dataset from scratch:** geocoded postal codes with the **OneMap API**, then pulled satellite tiles and
  Street View images through the **Google Maps APIs** with reproducible train / validation / test splits
- **Data integrity:** wrote augmentation and leak-checking tools so near-identical images never appear in
  both training and test sets, plus scripts that keep dataset metadata in sync
- **Modelling:** fine-tuned a **Faster R-CNN (ResNet-50 FPN v2)** detector in **PyTorch** with mixed-precision
  training, per-class precision / recall / F1 / mAP, early stopping, LR scheduling and crash-safe checkpointing
- **Delivery:** ran inference on unlabelled imagery and exported predictions as COCO JSON and CSV for the
  research team

Detected classes: solar panels, water tanks, laundry drying fixtures, and concrete and frame air-conditioner mounts.

**Stack:** `Python` `PyTorch` `torchvision` `Faster R-CNN` `Google Maps API` `OneMap API` `Label Studio` `COCO`

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

### 🎣 Illegal Fishing Detection

<sub><b>National Parks Board (NParks) &nbsp;·&nbsp; Internship &nbsp;·&nbsp; 2020 – 2021</b></sub>

A real-time detector that spots illegal fishing in park waters, built for an NParks patrol robot so that
staff no longer need to monitor hundreds of parks by hand. No suitable dataset existed, so I built one.

<table>
  <tr>
    <td align="center"><b>30–40 FPS</b><br><sub>real-time on video</sub></td>
    <td align="center"><b>&gt; 0.8</b><br><sub>mAP@0.5</sub></td>
    <td align="center"><b>15–20×</b><br><sub>faster than baseline</sub></td>
  </tr>
</table>

- **Data collection:** wrote a **Selenium** scraper, curated ~600 scraped images down to ~400 usable ones,
  then labelled, augmented and converted them to YOLO format
- **Model comparison:** benchmarked a **Keras YOLOv3** baseline (~2 FPS) against a tuned **YOLOv5** model
  that reached 30–40 FPS with mAP@0.5 above 0.8
- **Experimentation:** ran hyperparameter-tuning and focal-loss experiments, and validated on
  self-recorded footage as a real-world test set

**Stack:** `Python` `PyTorch` `YOLOv5` `Keras` `Selenium`

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

<h3><img src="assets/headers/tech-stack.svg" height="48" alt="Tech stack" /></h3>

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

| Area | Tools |
| :--- | :--- |
| **Languages** | ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![C#](https://img.shields.io/badge/C%23-512BD4?style=flat-square&logo=dotnet&logoColor=white) ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white) ![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black) |
| **ML & Computer Vision** | ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white) ![Keras](https://img.shields.io/badge/Keras-D00000?style=flat-square&logo=keras&logoColor=white) ![YOLO](https://img.shields.io/badge/YOLO-111F68?style=flat-square&logo=yolo&logoColor=white) |
| **Simulation & Backend** | ![Unity](https://img.shields.io/badge/Unity-000000?style=flat-square&logo=unity&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| **Data & Geospatial** | ![Google Maps](https://img.shields.io/badge/Google_Maps_API-4285F4?style=flat-square&logo=googlemaps&logoColor=white) ![OpenStreetMap](https://img.shields.io/badge/OpenStreetMap-7EBC6F?style=flat-square&logo=openstreetmap&logoColor=white) ![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=flat-square&logo=selenium&logoColor=white) |
| **Tooling** | ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white) |

<h3><img src="assets/headers/get-in-touch.svg" height="48" alt="Get in touch" /></h3>

<p align="center"><img src="assets/divider.svg" width="100%" alt="" /></p>

I'm always happy to talk about computer vision, simulation, or internship and graduate opportunities.
Reach me at **[xiangyang.1a2@gmail.com](mailto:xiangyang.1a2@gmail.com)**.
