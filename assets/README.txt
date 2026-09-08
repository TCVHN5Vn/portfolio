Put your files here:

  mariem.jpg       -> your photo, next to your name at the top (square crop is best)

Demo videos, one per project on the Work section:

  labelling-demo.mp4   -> Automated annotation pipeline  (20s silent loop)
  tta-demo.mp4         -> Test-Time Adaptation project
  llm-demo.mp4         -> LLM assistant project

Optional cover images shown before each video plays:

  labelling-poster.jpg
  tta-poster.jpg
  llm-poster.jpg

Long-form video for the labelling.html project page:

  labelling-walkthrough.mp4         -> 75s walkthrough, has controls, loads on click
  labelling-walkthrough-poster.jpg

Names must match exactly (lowercase). If a file is missing, the page
shows a placeholder instead of breaking.

Encoding recipe for the homepage loops — keep them short and small,
they autoplay on page load and three of them share the bandwidth:

  ffmpeg -ss <start> -t 20 -i source.webm -an \
    -vf "fps=24,scale=1440:900:flags=lanczos" \
    -c:v libx264 -crf 29 -preset slow -pix_fmt yuv420p \
    -movflags +faststart out.mp4

16:10 (1440x900) matches the .media slot. Aim for under 1 MB.
