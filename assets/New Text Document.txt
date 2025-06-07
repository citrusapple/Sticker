@echo off
REM This script converts PNG sequence to transparent .webm using ffmpeg

SET INPUT_DIR=C:\CodingProjects\Sticker\assets\testcircleanimations.png
SET OUTPUT_FILE=C:\CodingProjects\Sticker\assets\circleanimation.webm

ffmpeg -framerate 30 -i "%INPUT_DIR%\frame%%04d.png" -c:v libvpx -pix_fmt yuva420p -auto-alt-ref 0 -crf 15 -b:v 0 -y "%OUTPUT_FILE%"

echo Done! Output saved to:
echo %OUTPUT_FILE%
pause