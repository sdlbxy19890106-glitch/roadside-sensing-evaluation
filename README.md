# Time Alignment and Object Matching in Drone-Based Evaluation of Roadside Sensing Systems

This repository accompanies the study of how time alignment and object matching affect the measured performance of a roadside sensing system. The urban field experiment compares trajectories derived from overhead video with detections reported by a roadside computing unit. A highway sample provides a second setting for the position-error experiment.

## Watch the intersection recording

Download [intersection_clip.webm](intersection_clip.webm) to view the overhead recording used in the urban experiment. The clip contains 1,070 consecutive video frames covering the 106.885 seconds between the first and last of the 1,034 aerial reference records. The first video frame is frame 0. The public copy has been resized to 960 × 540 pixels. The recorder's on-screen telemetry is masked.

[frame-lookup.csv](frame-lookup.csv) relates elapsed time in the reference records to estimated frame numbers in the clip. Times are measured from the first reference record and the first clip frame, respectively. Frame numbers were inferred from the on-screen clock, which displayed whole seconds, and the sequence of frames. The selected alignment agreed with 60 of 63 checks against the on-screen clock. The recording and the reference lists lacked an independent frame-level synchronization signal.

For a visual check, go to frame 143 (about 14.3 seconds) for the intersection scene in Figure 1, or frame 177 (about 17.7 seconds) for the case in Figure 5. The video includes intervening frames for which there is no separate aerial reference record. The numerical analysis uses the reference and roadside observations produced for the experiment.

## Reproduce Tables 1–3

Download and extract [analysis-materials.zip](analysis-materials.zip). From the extracted directory, run the following command with Python 3.

```sh
python analysis/reproduce.py --output results
```

The script reads six CSV files and writes the manuscript tables to `results/table_1.csv`, `results/table_2.csv` and `results/table_3.csv`. These report the vehicle groups, position errors and detection results, respectively. Further CSV outputs cover selection of calibration vehicles, the timing controls, class-specific results and changes in object assignments at different thresholds. The included `data/README.md` defines the fields, units and aggregation rules.

To draw the three summary figures, install Matplotlib 3.6 or later and run:

```sh
python analysis/reproduce.py --output results --plots
```

The numerical supplement starts from aggregated experimental outputs. The source field recording, the individual roadside and aerial object lists, and the software used to generate reference trajectories and perform multi-object evaluation are outside this release.
