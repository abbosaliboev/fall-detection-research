Full Progress + Development PPT Content Plan (20+ Slides)

⸻

Slide 1: Title Slide
	•	Title: Real-Time Fall Detection for Construction Sites using Pose Completion and Temporal Prediction
	•	Subtitle: Your Name | Department | Professor | Date

Slide 2: Motivation
	•	Why fall detection is important
	•	Statistics of construction site injuries
	•	Need for real-time, camera-based systems

Slide 3: Problems in Existing Work
	•	Sensor-based systems: expensive, non-scalable
	•	Old vision models: slow, not real-time
	•	Occlusion not handled
	•	Pre-fall not predicted

Slide 4: Our Objective
	•	Real-time fall detection
	•	Handle occlusion
	•	Predict fall before it happens (Pre-fall)
	•	Estimate time-to-fall (regression)
	•	Edge-compatible (Jetson, etc.)

Slide 5: System Overview Diagram
	•	Visual pipeline diagram:
[Frame] → [YOLOv8-pose] → [Pose Completion] → [CNN + Transformer] → [Classification + Regression]

Slide 6: Dataset Used
	•	UP-Fall (HAR-UP) dataset
	•	Contains RGB frames from Camera1.zip
	•	Manual annotation: Pre-fall & TTF

Slide 7: Data Preprocessing
	•	Frame extraction from zip
	•	YOLOv8-pose for 17 keypoints
	•	Format: x1, y1, x2, y2, …, x17, y17

Slide 8: Pose Completion
	•	Problem: Occlusion = missing joints
	•	Solution: MLP or AutoEncoder fills missing keypoints
	•	Lightweight for real-time

Slide 9: Sequence Modeling (CNN)
	•	Sliding window of pose vectors
	•	Local motion pattern extraction

Slide 10: Temporal Attention (Transformer Encoder)
	•	Captures important frames in time
	•	Focuses on motion before fall
	•	Efficient attention head

Slide 11: Dual Output Head
	•	Output 1: Classification (Fall / Pre-fall / No fall)
	•	Output 2: Regression (Time-to-fall in seconds)

Slide 12: Model Architecture Overview
	•	Full diagram of the network
	•	Layers and flow

Slide 13: Evaluation Metrics
	•	Accuracy, F1-score, Precision, Recall, FPS
	•	Real-time test target: 15+ FPS

Slide 14: Previous Work – Paper 1 (YOSAP)
	•	YOLOv8 + AlphaPose + KNN
	•	Pros: multi-person, practical
	•	Cons: no pre-fall, no attention, low FPS

Slide 15: Previous Work – Paper 2 (TCNTE)
	•	TCN + Transformer on pose data
	•	Real-time edge-ready
	•	No occlusion handling, no pre-fall

Slide 16: Previous Work – Paper 3 (TST)
	•	YOLOv8 + Time-Space Transformer
	•	Strong modeling, but slow and no pre-fall

Slide 17: Comparative Table

Model	Occlusion	Pre-fall	Regression	Attention	Real-time
YOSAP	❌	✅	❌	❌	❌
TCNTE	❌	❌	❌	⚠	✅
TST	❌	❌	❌	✅	❌
Ours	✅	✅	✅	✅	✅

Slide 18: Model Innovation Summary
	•	First to combine pose completion + attention + TTF regression
	•	Multi-person ready, real-time capable
	•	Fall prevention, not just detection

Slide 19: Development Progress
	•	Dataset: ✅
	•	Pose Extraction: ✅
	•	Pose Completion: ⏳
	•	Annotation (Pre-fall/TTF): ⏳
	•	Model Coding: ✅
	•	Training: ⏳
	•	Evaluation: planned

Slide 20: Technical Challenges
	•	Frame-label alignment
	•	Manual annotation time
	•	Keeping FPS high while adding complexity

Slide 21: Solutions to Challenges
	•	Use sliding window sync with timestamp
	•	Automate label propagation from anchors
	•	Use light transformer blocks

Slide 22: Deployment Plan
	•	ONNX export or TorchScript
	•	Jetson Orin or RTX GPU test
	•	Real-time webcam inference

Slide 23: Next Steps
	•	Finish training
	•	Validate on held-out video
	•	Run demo on real stream
	•	Write student abstract / paper

Slide 24: Conclusion
	•	Novel real-time fall detection for high-risk environments
	•	Practical and research value

Slide 25: Q&A Slide
	•	“Thank you! Questions?”
