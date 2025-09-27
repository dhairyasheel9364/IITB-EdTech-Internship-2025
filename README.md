IITB_INTERNSHIP

This report is based on the analysis of a rich and distinctive multimodal dataset titled “A Multisensor Dataset of South Asian Postgraduate Students Performing Mental Rotation Tasks.” The dataset was collected as part of an extensive study in cognitive science and affective computing. The central aim of this study was to examine how postgraduate students approach and solve complex spatial reasoning problems—specifically three-dimensional (3D) mental rotation tasks. Such tasks are widely acknowledged to be cognitively demanding and are commonly employed in research related to human cognition, spatial ability, and workload assessment. By recording data across multiple physiological and behavioral modalities, the study intended to uncover the underlying mechanisms of stress response, focus, fatigue, and emotional variation that accompany problem-solving in high cognitive load environments.

Eight participants (IDs 31–38) took part in the study, each contributing a full set of synchronized multimodal data streams. This synchronization enables accurate temporal alignment across modalities and supports robust cross-sensor analysis. A summary of the dataset contents is provided below:

EEG.csv – Brainwave activity (Delta, Theta, Alpha, Beta, Gamma) from four electrodes (TP9, AF7, AF8, TP10), along with raw voltages, head movement (accelerometer/gyroscope), and device signal quality indicators.

GSR.csv – Skin conductance and resistance measures, serving as markers of physiological arousal and stress.

IVT.csv / EYE.csv – High-resolution eye-tracking logs including gaze points, fixation durations, saccadic movements, and pupil diameter, useful for analyzing visual attention and scanning behavior.

TIVA.csv – Facial emotion probabilities (e.g., engagement, joy, confusion, frustration), facial action units, and head pose data derived from webcam-based affective analysis.

PSY.csv – Task-related records such as experimental condition, task difficulty, correctness of responses, reaction times, and event timestamps.

NSTLX.csv – Self-reported workload assessments based on NASA-TLX dimensions (mental demand, physical demand, effort, frustration, and perceived performance).

DLOT.xlsx – Observer-coded behavioral annotations logged at 10-second intervals, capturing states such as engagement or confusion.

ExternalEvents.csv & BlankScreenData.csv – Metadata on slide transitions, rest intervals, and visual stimuli phases, facilitating synchronization with physiological signals.

Each participant’s dataset exceeds one million rows, and the combined dataset amounts to roughly 800 MB of multimodal recordings. This makes it a substantial and valuable resource for developing models of human cognition and affect under challenging task conditions.
