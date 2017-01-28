# Multimedia Sample Files
Some multimedia sample files for non-commercial purposes.   
The video taken from the movie *The Hobbit An Unexpected Journey (2012)*  whose copyright belongs to *New Line Cinema*.   

crop=1920:800:0:140
## THAUJ.mkv

```sh
$ ffmpeg -i The.Hobbit.An.Unexpected.Journey.2012.BluRay.REMUX.1080p.AVC.DTS-HD.MA7.1.mkv -ss 00:09:50 -t 00:00:12 -c copy THAUJ.mkv
```
12s 43.2M   
AVC High@4.1 VBR 1080p   
DTS MA/Core7.1 48.0kHz    

## THAUJ-crf22-1080p.h264
```sh
$ ffmpeg -i THAUJ.mkv -vf crop=1920:800:0:140 -c:v libx264 -preset slow -crf 22 -an THAUJ-crf22-1080p.h264
```
12s 10.4M   
AVC CRF22 High@L5 1080p   

## THAUJ-crf22-1080p.hevc

```sh
ffmpeg -i THAUJ.mkv -vf crop=1920:800:0:140 -c:v libx265 -preset slow -crf 22 -an THAUJ-crf22-1080p.hevc
```

12s 8.45M   
HEVC CRF22 Main@L4 1080P


## THAUJ-1M.mkv
```sh
ffmpeg -i THAUJ.mkv -vf crop=1920:800:0:140 -c:v libx264 -preset slow -qp 0 -acodec copy Losslessness.mkv
ffmpeg -i Losslessness.mkv -vf scale=1280:534 -c:v libx264 -preset slow -crf 32 -ac 2 -c:a aac -b:a 128k THAUJ-1M.mkv
```
Video: H.264  CRF32 720p 
Audio: AAC 128k

## THAUJ-1M.mp4
```sh
ffmpeg -i THAUJ-1M.mkv -c copy THAUJ-1M.mp4
```
Video: H.264  CRF32 720p 
Audio: AAC 128k

## THAUJ-1M.ts
```sh
ffmpeg -i THAUJ-1M.mkv -c copy THAUJ-1M.ts
```
Video: H.264  CRF32 720p 
Audio: AAC 128k

## THAUJ-1M.webm
```sh
ffmpeg -i Losslessness.mkv -vf scale=1280:534 -c:v libvpx-vp9 -crf 50 -b:v 0 -ac 2 -c:a libopus -b:a 128k THAUJ-1M.webm
```
Video: VP9 CRF50 720p 
Audio: opus 128k

## THAUJ-1M.h264
```sh
ffmpeg -i THAUJ-1M.mkv -c copy THAUJ-1M.h264
```
Video: H.264  CRF32 720p  

## THAUJ-1M.hevc
```sh
ffmpeg -i Losslessness.mkv -vf scale=1280:534 -c:v libx265 -preset slow -crf 28 -an THAUJ-1M.hevc
```
Video: HEVC CRF28 720p   