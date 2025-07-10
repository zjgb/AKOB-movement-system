# Swarm mimicking human movement dynamics via Laban movement analysis in real time

We have contructed a system that captures human motion data in real time, extracts Laban Efforts and maps them on a Swarm, as described [here] (https://github.com/zjgb/AKOBxSiouxThesis).

SYSTEM OVERVIEW: 
<img width="1182" alt="interactive-overview2" src="https://github.com/user-attachments/assets/55ac3d39-31de-4e6f-9135-13a59d8a68c3" />

An interactive system was constructed. It requires a camera to capture a video stream with human motion (Fig. 5.A). In real-time, it recognizes the body pose, and the Laban effort parameters are computationally extracted (Fig. 5.B) and stored (Fig. 5.C). At this point, the mapping framework is integrated into the system (Fig. 5.D), taking extracted Laban Efforts as input rather than 3 slider values. Finally, it overlays the particle render (Fig. 5.F) with the input video, creating an interactive Human-Swarm experience (Fig. 5.E).

INSTALLATION GUIDE:

1. Install Touchdesigner: You can download the free non commercial version here: https://derivative.ca/product/touchdesigner-non-commercial/77

2. Install MediaPipe plugin for Touchdesigner from here: https://github.com/torinmb/mediapipe-touchdesigner

3. 
