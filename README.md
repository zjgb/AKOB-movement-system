# Swarm mimicking human movement dynamics via Laban movement analysis in real time

We have constructed a system that captures human motion data in real-time, extracts Laban Efforts, and maps them onto a Swarm, as described [here] (https://github.com/zjgb/AKOBxSiouxThesis).

<p align="center">
  <img src="https://github.com/user-attachments/assets/adb7115d-5c9d-4259-a60e-5d00e871b147" width="400" style="margin-right: 20px;" />
  <img src="https://github.com/user-attachments/assets/9a9c08fd-d99d-47ce-b2f6-9fa2706b614e" width="400" />
</p>



## SYSTEM OVERVIEW: 
<img width="1182" alt="interactive-overview2" src="https://github.com/user-attachments/assets/55ac3d39-31de-4e6f-9135-13a59d8a68c3" />

An interactive system was constructed. It requires a camera to capture a video stream with human motion (Fig. 5.A). In real-time, it recognises the body pose, and the Laban effort parameters are computationally extracted (Fig. 5.B) and stored (Fig. 5.C). At this point, the mapping framework is integrated into the system (Fig. 5.D), taking extracted Laban Efforts as input rather than 3 slider values. Finally, it overlays the particle render (Fig. 5.F) on top of the input video, creating an interactive Human-Swarm experience (Fig. 5.E).

## INSTALLATION GUIDE:

1. Install Touchdesigner: You can download the free non-commercial version here: https://derivative.ca/product/touchdesigner-non-commercial/77

2. Install MediaPipe plugin for Touchdesigner from here: https://github.com/torinmb/mediapipe-touchdesigner

3. Step 2 will download a folder called release. In that Folder, there is a TouchDesigner project file called MediaPipe TouchDesigner. Delete it and replace it with the MediaPipe TouchDesigner file in this repository.

6. If there is a problem with importing libraries, check this video: https://www.youtube.com/watch?v=jUouJcGDRPk&t=1s

7. For a better view, you can open comp1 (overlaid video and particles) as a separate Window (make sure Viewer active is unchecked, right click on the frame and choose "Open as Separate Window").


### STILL WORKING ON NORMALISING THE VALUES:

Since the human Laban Efforts are extracted in various ranges, we need to find an efficient way to map the values between 0 and 1 (input for Laban to Swarm mapping). The growth is not linear. Current method: 

1. We stored the raw Human Effort values from testing out the framework with various movements (including min and max of all parameters, trying to find a distribution)
2. We visualised the distribution by plotting the values in a histogram and then extracted 20 percentiles and their respective values on the plot (for example Human Time at 10th percentile is 0.07, at 50th percentile it is 0.4, at 90th percentile it is 1.3)
3. Using the numpy.interp() function, we infer the mapped values at a specific Human Effort value.
4. Due to normalisation problems, MediaPipe TouchDesigner.td works best for Time representation, and MediaPipe TouchDesigner.2.td works best for Weight representation
5. Please reach out if you have tips on how to do this better 
