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

## THAUJ-crf22.h264
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