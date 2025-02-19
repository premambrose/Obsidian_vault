Here's a bash script that compresses all the videos in a folder using ffmpeg and nvidia hardware acceleration:

```
#!/bin/bash

# Set the input and output folders
input_folder="/path/to/input/folder"
output_folder="${input_folder}/compressed"

# Create the output folder if it doesn't exist
mkdir -p "${output_folder}"

# Loop through all the videos in the input folder
for video in "${input_folder}"/*.mp4; do
  # Get the filename without the extension
  filename=$(basename "${video}" .mp4)

  # Compress the video using ffmpeg and nvidia hardware acceleration
  ffmpeg -hwaccel cuvid -i "${video}" -c:v hevc_nvenc -rc cbr_ld_hq -b:v 2M -maxrate:v 2M -bufsize:v 2M -pix_fmt yuv420p -r 20 -c:a copy "${output_folder}/${filename}.mp4"
done
```

This script assumes that all the videos in the input folder have the `.mp4` extension. If your videos have a different extension, you'll need to modify the script accordingly.

The script uses the `mkdir` command to create the output folder if it doesn't exist. The `-p` option tells `mkdir` to create the parent directories if they don't exist.

The script then loops through all the videos in the input folder using a `for` loop. For each video, it uses `ffmpeg` to compress the video using the `hevc_nvenc` codec with a constant frame rate of 20 frames per second (`-c:v hevc_nvenc -r 20`). It also sets the bitrate to 2 Mbps (`-b:v 2M -maxrate:v 2M -bufsize:v 2M`) and the pixel format to yuv420p (`-pix_fmt yuv420p`). The audio is copied without any compression (`-c:a copy`).

The compressed video is saved in the output folder with the same filename as the original video, but with the `.mp4` extension.

Note that this script requires an NVIDIA GPU with the NVENC encoder. If you don't have an NVIDIA GPU, you'll need to modify the script to use a different encoder.