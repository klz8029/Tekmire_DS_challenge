# AI Collaboration Note

## Did You Use AI?
Yes, I collaborated with Gemini throughout the development of this project.

## How You Used It
I used AI as a coding assistant and analytical partner to write Python data cleaning scripts, construct metrics (such as weighted acceptance rates), and build line plot visualizations using Pandas, Matplotlib, and Seaborn.

## One Prompt, Workflow, Or Moment That Helped
Refining the visualization workflow: *"Create a plot for acceptance rate over time for each workflow, and label the major events with vertical markers."* This visually highlighted how the August 4 prompt upgrade boosted performance while the August 7 policy change caused a drop in Support workflow efficiency.

## One Thing You Verified Or Decided Yourself
I independently verified why the shaded confidence band disappeared on the final day of the plot—discovering it was due to telemetry only logging a single entry source on August 7—and decided to use weighted volume averages ($\sum \text{accepted} / \sum \text{completed}$) rather than simple daily averages to accurately evaluate performance across varying session volumes.
