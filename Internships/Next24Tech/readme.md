# Road Lane Line Detection

## Overview

This script utilizes computer vision techniques to detect and visualize lane lines in images and videos. It processes each frame to identify lane markings using edge detection and the Hough transform.

### custom_region()
Creates a mask to isolate a polygonal region of interest within the input image, focusing on where lane lines are expected.

### custom_hough()
Applies the probabilistic Hough transform to detect straight lines in edge-detected images generated using the Canny algorithm. Parameters such as rho, theta, threshold, minLineLength, and maxLineGap are specified to accurately identify potential lane markings.

### calculate_slope_intercept()
Categorizes detected lines into left and right lane groups based on their slopes. Computes average slope and intercept, weighted by line lengths for accurate lane detection.

### calculate_pixel_points()
Converts slope and intercept parameters into pixel coordinates defining lane line endpoints on the image, ensuring correct positioning within the frame.

### detect_lane_lines()
Integrates slope-intercept calculations to identify left and right lane lines within the image. Processes detected lines and computes pixel coordinates for lane markings.

### draw_detected_lines()
Overlays detected lane lines onto the original image using specified color and thickness parameters, aiding visualization and evaluation.

### process_frame()
Orchestrates lane detection for a single image or video frame. Converts to grayscale, applies Gaussian blur, edge detection, region of interest masking, Hough line detection, and overlays detected lane lines.

### process_video()
Automates lane detection across all frames of a video. Utilizes `process_frame` to process each frame sequentially, detect lane lines, and output an annotated video with lane markings.
