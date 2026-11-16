<!--
  HOW TO USE THIS FILE
  - Anything inside these comment markers is invisible on your profile, so the tips can stay or go.
  - Replace every [BRACKETED] placeholder, and delete any line you can't fill in yet.
  - Keep it short: visitors spend roughly 10 seconds here. Lead with who you are and your best work.
-->

# Hi, I'm Xiang Yang (axewhy) 👋

I'm a Computer Science student at **DigiPen Institute of Technology Singapore** who likes turning
real-world images into useful data. Most of my work sits where **computer vision**, **machine
learning** and **simulation** meet: training detectors on data I collect myself, and building
software that helps people train for autonomous vehicles.

## 🧭 About me

- 🎓 Year 3 **Computer Science** at **DigiPen Singapore**, graduating **2028**
- 🔭 Currently building **Formula 9**, an autonomous-shuttle fleet training simulator, with a team of 8
- 🧪 Interned at the **National Environment Agency (NEA)**, **National Park Board (NParks)**
- 🔌 Before DigiPen: **Diploma in Electronic & Computer Engineering**, **Ngee Ann Polytechnic**

## 🛠️ Tech I use

<!--
  Badges come from https://shields.io (logo names: https://simpleicons.org).
  Only keep tools you could talk about in an interview. The second row is from Formula 9:
  delete any you didn't personally work with.
-->

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

![C#](https://img.shields.io/badge/C%23-512BD4?style=flat&logo=dotnet&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-000000?style=flat&logo=unity&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)

## 🚀 Featured projects

<!--
  Both repositories are PRIVATE right now, so they have no links: a visitor clicking one would get a 404.
  Once a repo is public (see the notes in our chat first), turn its title into a link, e.g.
  ### [🏢 HDB Feature Detection](https://github.com/axewhy-xy/NEA_Internship_April_2026)
  A screenshot or GIF under each title helps a lot: store it in the project's repo and link it here.
-->

### 🚐 Formula 9 · Autonomous shuttle fleet training simulator (team project, in progress)

A training simulator where operators manage a fleet of autonomous shuttles on real Singapore streets,
handling incidents, detours and charging. A Unity client talks to a Python/FastAPI backend that runs
the simulation, and the whole thing ships as a one-click Windows build.

- **Backend:** Designed the backend architecture, wrote the simulation loop and vehicle physics, and implemented
  the API for the Unity client to talk to.
- **Unity Client:** Built the 3D world, vehicle models, and UI, and implemented the client-side logic for
  incidents, detours and charging.
- **Data Pipeline:** Wrote scripts to convert OpenStreetMap data into Unity terrain, and to generate
  realistic traffic and pedestrian patterns for the simulation.
- **Testing & Deployment:** Set up automated testing and continuous integration, and created a one-click
  Windows build for easy deployment.

### 🏢 HDB Feature Detection for Wolbachia Release Planning · NEA internship (2026)

An end-to-end computer-vision pipeline that finds building features linked to mosquito activity in
images of Singapore's HDB blocks, to help plan *Wolbachia-Aedes* mosquito releases.

- Built the dataset from scratch: scripts that turn postal codes into coordinates (OneMap API) and pull
  satellite tiles and Street View images (Google Maps APIs), with automatic train/valid/test splits
- Wrote augmentation and leak-checking tools so near-identical images never land in both training and test sets
- Fine-tuned a **Faster R-CNN (ResNet-50)** detector in **PyTorch**, with per-class metrics, early stopping,
  LR scheduling and crash-safe checkpointing
- Ran the model on unlabelled images and exported predictions as COCO JSON / CSV for the research team

`Python` `PyTorch` `Faster R-CNN` `Google Maps API` `COCO`


`C#` `Unity` `Python` `FastAPI` `MongoDB`

### 🎣 Illegal Fishing Detection for NParks · National Parks Board (2020–21)

A real-time detector that spots fishing in park waters, built for a National Parks Board patrol robot so
staff wouldn't have to watch hundreds of parks by hand. No fishing dataset existed, so I built one.

- Wrote a **Selenium** web scraper to collect images, cleaned ~600 scraped images down to ~400 usable
  ones, then labelled, augmented and converted them to YOLO format
- Trained and compared two detectors: a **Keras YOLOv3** baseline (~2 FPS) and a tuned **YOLOv5**
  model that ran at **~30–40 FPS** on video with **mAP@0.5 above 0.8**
- Ran hyperparameter-tuning and focal-loss experiments, and tested on my own recorded footage
  as a real-world test set

`Python` `YOLOv5` `Keras` `PyTorch` `Selenium`

<!--
  OPTIONAL: past projects that aren't on GitHub. A one-line description is still worth showing,
  linked to a video, itch.io page or write-up if you have one. Delete this section if you have nothing to link.

### 🗂️ Other things I've built

- **[PROJECT NAME]**: [ONE LINE: what it is + the tech]. [Video](https://LINK)
- **[PROJECT NAME]**: [ONE LINE]. [Write-up](https://LINK)
-->

## 📫 Get in touch

<!-- Only add contact details you're happy for anyone on the internet to see. -->

- ✉️ Email: xiangyang.1a2@gmail.com
