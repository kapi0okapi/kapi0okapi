<div align="center">

# Hello there. 🌌⚔️ I'm Kacper 👋

### AI Engineer · Computer Vision & 3D Perception

<a href="https://kacperpawlowski.tech">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1200&color=FF4F1A&center=true&vCenter=true&width=640&lines=Detection+%C2%B7+Segmentation+%C2%B7+Depth;LiDAR+SLAM+%C2%B7+Visual+odometry+%C2%B7+Sensor+fusion;From+raw+sensor+data+to+deployed+models" alt="Detection, segmentation, depth, LiDAR SLAM, from raw sensor data to deployed models" />
</a>

</div>

I build computer vision and 3D perception systems end to end: the data pipeline, the model, an
honest evaluation against an independent reference, and deployment on the hardware it has to run
on. AI engineer at Lighthouse Consulting (visual inspection and predictive maintenance) and MSc
student at NTNU in Trondheim (Computer Science with AI, and Industrial Mathematics).

```json
{
  "role": "AI Engineer",
  "focus": ["computer vision", "3D perception", "edge AI"],
  "now": "AI engineer @ Lighthouse Consulting",
  "education": "MSc @ NTNU, AI & Industrial Mathematics",
  "website": "kacperpawlowski.tech"
}
```

---

## 🔭 Projects

Every project starts from raw data and ends with a number I can defend. Where a project
reimplements a published method, its README compares my results with the paper's.

> **Not everything is here.** Much of my professional work is covered by NDAs, and some projects
> are still being built or have not been published yet. The repositories below are my own work,
> open source and reproducible, and new ones are added as they are finished.

### Computer Vision · Detection & Tracking

| Project                                                                                | What it does                                                                                                                                                                                       | Demo                                                                                                                                          |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **[vaktsom](https://github.com/kapi0okapi/vaktsom)**                                   | Detects drowning in public swimming pools and alerts the lifeguards. An RF-DETR detector trained on Blender renders from ceiling cameras, 3D tracking of every bather through the water surface from several cameras, and ISO 20380 alarm rules: all **200** simulated ISO tests passed, with no false alarms. | <img src="assets/vaktsom.gif" width="300" alt="A ceiling camera over a pool: boxes around swimmers, a distress warning, then the bottom alarm on the sinking person"> |
| **[vehicle-counter](https://github.com/kapi0okapi/vehicle-counter)**                   | Counts vehicles in traffic video. Detects cars and trucks with YOLO26, follows each one from frame to frame with tracking algorithms such as ByteTrack and BoT-SORT, and counts it once when it crosses a line: **2.7 %** counting error on traffic cameras it never saw. | <img src="assets/vehicle-counter.gif" width="300" alt="Vehicles with track ids counted as they cross a line on a traffic camera">                                                      |
| **[hand-gesture-recognition](https://github.com/kapi0okapi/hand-gesture-recognition)** | Recognises hand gestures from a camera. Compares small neural networks on hand keypoints from MediaPipe with a YOLO26 detector that looks at the whole image (**99.3 %** of gestures right).       | <img src="assets/hand-gesture-recognition.gif" width="300" alt="Hands in video clips with the MediaPipe skeleton and the recognised gesture"> |

### Computer Vision · Segmentation

| Project                                                                              | What it does                                                                                                                                                                                                         | Demo                                                                                                               |
| ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| **[road-scene-segmentation](https://github.com/kapi0okapi/road-scene-segmentation)** | Labels every pixel of a road scene: road, cars, signs and guard rails. Compares seven segmentation models, including YOLO26, SegFormer and Mask2Former, and teaches one of them to find guard rails.                 | <img src="assets/segmentation.gif" width="300" alt="Semantic segmentation of a Norwegian motorway">                |
| **[clock-reader](https://github.com/kapi0okapi/clock-reader)**                       | Reads the time from a photo of an analogue clock. A U-Net in PyTorch, trained only on generated images, finds the hands, and geometry turns them into a time. **98.6 %** of tilted clocks are read within 5 minutes. | <img src="assets/clock-reader.gif" width="300" alt="Clock read step by step: photo, segmentation, rectified dial"> |

### Vision-Language · Search & RAG

| Project | What it does | Demo |
| --- | --- | --- |
| **[multimodal-image-search](https://github.com/kapi0okapi/multimodal-image-search)** | Finds photos from a sentence or from another photo, and answers questions about a photo collection with citations to the photos it used. SigLIP 2 and Perception Encoder embeddings are fused in one FAISS index and reranked by the Qwen3-VL vision-language model: the right photo comes first in **89.7 %** of Flickr30k searches, ahead of every single published model it is compared with. | <img src="assets/multimodal-image-search.gif" width="300" alt="Search by text and by photo, and a question answered with citations to four photos"> |

### Depth, 3D Perception & SLAM

| Project                                                                              | What it does                                                                                                                                                                                                                                                              | Demo                                                                                                                             |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| **[monocular-depth](https://github.com/kapi0okapi/monocular-depth)**                 | Estimates distance from a single camera image. Compares eleven depth models, including Depth Anything and Depth Pro, on the KITTI driving dataset, and fine-tunes a real-time YOLO26 model that measures distance in metres more accurately than the large metric models. | <img src="assets/depth.gif" width="300" alt="Depth map of a motorway video">                                                     |
| **[lidar-slam](https://github.com/kapi0okapi/lidar-slam)**                           | Tracks a car's position and builds a map from LiDAR scans (SLAM). My own implementation of KISS-ICP with loop closure drifts **0.63 %** over all of the KITTI dataset.                                                                                                    | <img src="assets/lidar-slam.gif" width="300" alt="LiDAR map of KITTI 00 growing along the trajectory, with loop closures">       |
| **[lidar-road-segmentation](https://github.com/kapi0okapi/lidar-road-segmentation)** | Classifies 3D LiDAR points along a road, such as road, cars and guard rails, with a RandLA-Net network in PyTorch (**81.8** mIoU, same as the paper), then measures guard-rail height from the result.                                                                    | <img src="assets/lidar-road-segmentation.gif" width="300" alt="Rotating Toronto-3D street point cloud classified by RandLA-Net"> |
| **[gnss-ins-fusion](https://github.com/kapi0okapi/gnss-ins-fusion)**                 | Combines GPS and motion-sensor (IMU) data with a Kalman filter for a smooth, accurate position, even when GPS drops out in tunnels. Tested on real KITTI drives.                                                                                                          | <img src="assets/gnss-ins-fusion.gif" width="300" alt="KITTI drive with GNSS outages bridged by the IMU">                        |

### Visual Inspection

| Project                                                                                | What it does                                                                                                                                                                                                             | Demo                                                                                                                                |
| -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| **[visual-anomaly-detection](https://github.com/kapi0okapi/visual-anomaly-detection)** | Finds defects in product images after learning only from good ones. PatchCore and PaDiM built in PyTorch, close to the published results on the VisA benchmark (AUROC **0.914**).                                        | <img src="assets/visual-anomaly-detection.gif" width="300" alt="Anomaly maps on VisA candles, circuit boards and cashews">          |
| **[guardrail-inspector](https://github.com/kapi0okapi/guardrail-inspector)**           | Checks road photos against Norway's road database. Trains image classifiers in PyTorch on 30,000 photos labelled automatically from map data (**0.98** AP for guard rails), and maps where photos and database disagree. | <img src="assets/guardrail-inspector.gif" width="300" alt="Drive along the E6 with the guard-rail model next to the road register"> |
| **[inspection-platform](https://github.com/kapi0okapi/inspection-platform)**           | A web platform that compares AI results with Norway's road database, built with PostgreSQL/PostGIS, FastAPI, an interactive map, Docker and Terraform for AWS. The guard-rail model reaches **91 %** precision.          | <img src="assets/inspection-platform.jpg" width="300" alt="Map of model results against the road register">                         |

### Drones

| Project                                                                            | What it does                                                                                                                                                                                                 | Demo                                                                                                              |
| ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **[drone-object-detection](https://github.com/kapi0okapi/drone-object-detection)** | Finds people and vehicles in drone photos, where most objects are tiny. Trains YOLO26 on image tiles instead of shrunk photos, which nearly doubles the accuracy on small objects (**26.5** AP on VisDrone). | <img src="assets/drone-detection.gif" width="300" alt="Detections of cars and people from a drone">               |
| **[drone-landing-zones](https://github.com/kapi0okapi/drone-landing-zones)**       | Decides where a drone can land safely. A YOLO26 segmentation model labels the ground below, and a rule in metres picks the nearest clear spot away from people: **94 %** safe decisions on unseen photos.    | <img src="assets/drone-landing.gif" width="300" alt="Landing spot re-planned while people move through a garden"> |

### Edge AI & Deployment

| Project                                                                  | What it does                                                                                                                                                                                                                                 | Demo                                                                                                                       |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **[edge-optimization](https://github.com/kapi0okapi/edge-optimization)** | Makes a YOLO26 detector three times smaller for edge devices with INT8 quantization (ONNX Runtime, OpenVINO, Core ML, TensorRT). Keeps **97 %** of the accuracy, ahead of quantization-aware training, and runs up to 2x faster on x86 CPUs. | <img src="assets/edge-optimization.gif" width="300" alt="One street photo through FP32 and three INT8 exports of YOLO26n"> |

### Face Analysis

| Project                                                            | What it does                                                                                                                                                                                                            | Demo                                                                                                                           |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **[age-estimation](https://github.com/kapi0okapi/age-estimation)** | Estimates a person's age from a face photo with a ConvNeXt network, after aligning the face with MediaPipe, and reports the error separately for age groups, genders and ethnicities. Off by **4.25** years on average. | <img src="assets/age-estimation.gif" width="300" alt="Face landmarks, alignment and the predicted age next to the actual age"> |

More on **[kacperpawlowski.tech](https://kacperpawlowski.tech)**: project write-ups, technical articles
(English, Norwegian, Polish) and a lab where four of these models run in your browser.

---

## 🛠️ Tech Stack

The AI and computer vision stack first, then everything else I build with.

### 🧠 AI, Deep Learning & Computer Vision

<p align="left">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch" />
  <img src="https://img.shields.io/badge/Ultralytics_YOLO26-111F68?style=for-the-badge&logo=ultralytics&logoColor=white" alt="Ultralytics YOLO26" />
  <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
  <img src="https://img.shields.io/badge/Hugging_Face-FFAA21?style=for-the-badge&logo=huggingface&logoColor=white" alt="Hugging Face" />
  <img src="https://img.shields.io/badge/FAISS-0467DF?style=for-the-badge&logo=meta&logoColor=white" alt="FAISS" />
  <img src="https://img.shields.io/badge/timm-4B5563?style=for-the-badge" alt="timm" />
  <img src="https://img.shields.io/badge/MediaPipe-0097A7?style=for-the-badge&logo=mediapipe&logoColor=white" alt="MediaPipe" />
  <img src="https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="scikit-learn" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy" />
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white" alt="SciPy" />
  <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white" alt="Jupyter" />
  <img src="https://img.shields.io/badge/JAX-Accelerated-9cf.svg?style=for-the-badge&logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC0AAAAaCAYAAAAjZdWPAAAIx0lEQVR42rWWBVQbWxOAkefur%2B7u3les7u7F3ZIQ3N2tbng8aXFC0uAuKf2hmlJ3AapIgobMv7t0w%2Ba50JzzJdlhlvNldubeq%2FY%2BXrTS1z%2B6sttrKfQOOY4ns13ecFImb47pVvIkukNe4y3Junr1kSZ%2Bb3Na248tx7rKiHlPo6Ryse%2F11NKQuk%2FV3tfL52yHtXm8TGYS1wk4J093wrPQPngRJH9HH1x2fAjMhcIeIaXKQCmd2Gn7IqSvG83BueT0CMkTyESUqm3vRRggTdOBIb1HFDaNl8Gdg91AFGkO7QXe8gJInpoDjEXC9gbhtWH3rjZ%2F9yK6t42Y9zyiC1iLhZA8JQe4eqKXklrJF0MqfPv2bc2wzPZjpnEyMEVlEZCKQzYCJhE8QEtIL1RaXEVFEGmEaTn96VuLDzWflLFbgvqUec3BPVBmeBnNwUiakq1I31UcPaTSR8%2B1LnditsscaB2A48K6D9SoZDD2O6bELvA0JGhl4zIYZzcWtD%2BMfdvdHNsDOHciXwBPN18lj7sy79qQCTNK3nxBZXakqbZFO2jHskA7zBs%2BJhmDmr0RhoadIZjYxKIVHpCZngPMZUKoQKrfEoz1PfZZdKAe2CvP4XnYE8k2LLMdMumwrLaNlomyVqK0UdwN%2BD7AAz73dYBpPg6gPiCN8TXFHCI2s7AWYesJgTabD%2FS5uXDTuwVaAvvghncTdk1DYGkL0daAs%2BsLiutLrn0%2BRMNXpunC7mgkCpshfbw4OhrUvMkYo%2F0c4XtHS1waY4mlG6To8oG1TKjs78xV5fAkSgqcZSL0GoszfxEAW0fUludRNWlIhGsljzVjctr8rJOkCpskKaDYIlgkVoCmF0kp%2FbW%2FU%2F%2B8QNdXPztbAc4kFxIEmNGwKuI9y5gnBMH%2BakiZxlfGaLP48kyj4qPFkeIPh0Q6lt861zZF%2BgBpDcAxT3gEOjGxMDLQRSn9XaDzPWdOstkEN7uez6jmgLOYilR7NkFwLh%2B4G0SQMnMwRp8jaCrwEs8eEmFW2VsNd07HQdP4TgWxNTYcFcKHPhRYFOWLfJJBE5FefTQsWiKRaOw6FBr6ob1RP3EoqdbHsWFDwAYvaVI28DaK8AHs51tU%2BA3Z8CUXvZ1jnSR7SRS2SnwKw4O8B1rCjwrjgt1gSrjXnWhBxjD0Hidm4vfj3e3riUP5PcUCYlZxsYFDK41XnLlUANwVeeILFde%2BGKLhk3zgyZNeQjcSHPMEKSyPPQKfIcKfIqCf8yN95MGZZ1bj98WJ%2BOorQzxsPqcYdX9orw8420jBQNfJVVmTOStEUqFz5dq%2F2tHUY3LbjMh0qYxCwCGxRep8%2FK4ZnldzuUkjJLPDhkzrUFBoHYBjk3odtNMYoJVGx9BG2JTNVehksmRaGUwMbYQITk3Xw9gOxbNoGaA8RWjwuQdsXdGvpdty7Su2%2Fqn0qbzWsXYp0nqVpet0O6zzugva1MZHUdwHk9G8aH7raHua9AIxzzjxDaw4w4cpvEQlM84kwdI0hkpsPpcOtUeaVM8hQT2Qtb4ckUbaYw4fXzGAqSVEd8CGpqamj%2F9Q2pPX7miW0NlHlDE81AxLSI2wyK6xf6vfrcgEwb0PAtPaHM1%2BNXzGXAlMRcUIrMpiE6%2Bxv0cyxSrC6FmjzvkWJE3OxpY%2BzmpsANFBxK6RuIJvXe7bUHNd4zfCwvPPh9unSO%2BbIL2JY53QDqvdbsEi2%2BuwEEHPsfFRdOqjHcjTaCLmWdBewtKzHEwKZynSGgtTaSqx7dwMeBLRhR1LETDhu76vgTFfMLi8zc8F7hoRPpAYjAWCp0Jy5dzfSEfltGU6M9oVCIATnPoGKImDUJNfK0JS37QTc9yY7eDKzIX5wR4wN8RTya4jETAvZDCmFeEPwhNXoOlQt5JnRzqhxLZBpY%2BT5mZD3M4MfLnDW6U%2Fy6jkaDXtysDm8vjxY%2FXYnLebkelXaQtSSge2IhBj9kjMLF41duDUNRiDLHEzfaigsoxRzWG6B0kZ2%2BoRA3dD2lRa44ZrM%2FBW5ANziVApGLaKCYucXOCEdhoew5Y%2Btu65VwJqxUC1j4lav6UwpIJfnRswQUIMawPSr2LGp6WwLDYJ2TwoMNbf6Tdni%2FEuNvAdEvuUZAwFERLVXg7pg9xt1djZgqV7DmuHFGQI9Sje2A9dR%2FFDd0osztIRYnln1hdW1dff%2B1gtNLN1u0ViZy9BBlu%2BzBNUK%2BrIaP9Nla2TG%2BETHwq2kXzmS4XxXmSVan9KMYUprrbgFJqCndyIw9fgdh8dMvzIiW0sngbxoGlniN6LffruTEIGE9khBw5T2FDmWlTYqrnEPa7aF%2FYYcPYiUE48Ul5jhP82tj%2FiESyJilCeLdQRpod6No3xJNNHeZBpOBsiAzm5rg2dBZYSyH9Hob0EOFqqh3vWOuHbFR5eXcORp4OzwTUA4rUzVfJ4q%2FIa1GzCrzjOMxQr5uqLAWUOwgaHOphrgF0r2epYh%2FytdjBmUAurfM6CxruT3Ee%2BDv2%2FHAwK4RUIPskqK%2Fw4%2FR1F1bWfHjbNiXcYl6RwGJcMOMdXZaEVxCutSN1SGLMx3JfzCdlU8THZFFC%2BJJuB2964wSGdmq3I2FEcpWYVfHm4jmXd%2BRn7agFn9oFaWGYhBmJs5v5a0LZUjc3Sr4Ep%2FmFYlX8OdLlFYidM%2B731v7Ly4lfu85l3SSMTAcd5Bg2Sl%2FIHBm3RuacVx%2BrHpFcWjxztavOcOBcTnUhwekkGlsfWEt2%2FkHflB7WqKomGvs9F62l7a%2BRKQQQtRBD9VIlZiLEfRBRfQEmDb32cFQcSjznUP3um%2FkcbV%2BjmNEvqhOQuonjoQh7QF%2BbK811rduN5G6ICLD%2BnmPbi0ur2hrDLKhQYiwRdQrvKjcp%2F%2BL%2BnTz%2Fa4FgvmakvluPMMxbL15Dq5MTYAhOxXM%2FmvEpsoWmtfP9RxnkAIAr%2F5pVxqPxH93msKodRSXIct2l0OU0%2FL4eY506L%2B3GyJ6UMEZfjjCDbysNcWWmFweJP0Jz%2FA0g2gk80pGkYAAAAAElFTkSuQmCC" alt="JAX" />
</p>

### 📐 3D Perception, LiDAR & Sensor Fusion

<p align="left">
  <img src="https://img.shields.io/badge/LiDAR_point_clouds-0A9EC2?style=for-the-badge" alt="LiDAR point clouds" />
  <img src="https://img.shields.io/badge/SLAM_%26_odometry-0E1013?style=for-the-badge" alt="SLAM and odometry" />
  <img src="https://img.shields.io/badge/Kalman_filters-6A7078?style=for-the-badge" alt="Kalman filters" />
  <img src="https://img.shields.io/badge/GNSS_%2F_IMU-6AA318?style=for-the-badge" alt="GNSS and IMU" />
  <img src="https://img.shields.io/badge/laspy_(LAS%2FLAZ)-4B5563?style=for-the-badge" alt="laspy" />
</p>

### ⚡ Model Deployment & MLOps

<p align="left">
  <img src="https://img.shields.io/badge/ONNX_Runtime-005CED?style=for-the-badge&logo=onnx&logoColor=white" alt="ONNX Runtime" />
  <img src="https://img.shields.io/badge/TensorRT-76B900?style=for-the-badge&logo=nvidia&logoColor=white" alt="TensorRT" />
  <img src="https://img.shields.io/badge/OpenVINO-0071C5?style=for-the-badge&logo=intel&logoColor=white" alt="OpenVINO" />
  <img src="https://img.shields.io/badge/Core_ML-000000?style=for-the-badge&logo=apple&logoColor=white" alt="Core ML" />
  <img src="https://img.shields.io/badge/INT8_%26_QAT-FF4F1A?style=for-the-badge" alt="INT8 quantization and QAT" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform" />
  <img src="https://img.shields.io/badge/Slurm_GPU_cluster-4B5563?style=for-the-badge&logo=linux&logoColor=white" alt="Slurm GPU cluster" />
</p>

### 🗺️ Geospatial Data

<p align="left">
  <img src="https://img.shields.io/badge/PostGIS-336791?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostGIS" />
  <img src="https://img.shields.io/badge/GeoPandas-139C5A?style=for-the-badge" alt="GeoPandas" />
  <img src="https://img.shields.io/badge/MapLibre-396CB2?style=for-the-badge&logo=maplibre&logoColor=white" alt="MapLibre" />
</p>

### 💻 Languages

<p align="left">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white" alt="C#" />
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" alt="C++" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" />
  <img src="https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white" alt="R" />
  <img src="https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white" alt="Bash" />
</p>

### 🎨 Frontend & Design

<p align="left">
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS" />
  <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap" />
  <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=figma&logoColor=white" alt="Figma" />
</p>

### ⚙️ Backend & APIs

<p align="left">
  <img src="https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
  <img src="https://img.shields.io/badge/Express.js-404D59?style=for-the-badge&logo=express&logoColor=white" alt="Express.js" />
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django" />
  <img src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
</p>

### 🗄️ Databases & ORMs

<p align="left">
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB" />
  <img src="https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite" />
  <img src="https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase" />
</p>

### ☁️ Cloud, DevOps & Hosting

<p align="left">
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
  <img src="https://img.shields.io/badge/Microsoft_Azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white" alt="Azure" />
  <img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS" />
  <img src="https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" alt="GCP" />
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux" />
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu" />
  <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx" />
</p>

### 📱 Mobile & Game Dev

<p align="left">
  <img src="https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white" alt="Flutter" />
  <img src="https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React Native" />
  <img src="https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white" alt="Unity" />
</p>

---

## 📫 Let's connect

<div align="center">
  <a href="https://kacperpawlowski.tech">
    <img src="https://img.shields.io/badge/Website-FF4F1A?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Website" />
  </a>
  <a href="mailto:contact@kacperpawlowski.tech">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://www.linkedin.com/in/kacper-pawlowski-914ab8297/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
</div>
