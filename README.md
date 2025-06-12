# AI Subtitle Translator

A Python script to translate SubRip (.srt) subtitles using AI (g4f).

## Description

The script takes an input .srt file and translates the subtitle text from a specified input language to a specified output language, using an AI model (GPT-4) from [gpt4free](https://github.com/xtekky/gpt4free). The translation consists of two steps: initial (direct) translation and final adaptation, correcting translation errors and gender mismatches (based on characters names and entire translated text). The final translated subtitles are saved to a new .srt file. No API/token is needed.

## Dependencies

1. Generate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate
```

2. Install dependences

```bash
pip install g4f\[all\] argparse pycountry tqdm colorama
```

3. ffmpeg must be installed

## Usage

_(Available languages: [ISO 639-2 Codes](https://www.loc.gov/standards/iso639-2/php/code_list.php))_

**Help**:

```
$ python srt-ai-translator.py -h

usage: srt-ai-translator.py [-h] [-o OUTPUT_FOLDER] [--demux [DEMUX]] [--delete]
                            input_path input_lang output_lang

translate SRT file(s) using gpt4free.

positional arguments:
  input_path            input path for the .srt file or folder containing .srt files
  input_lang            input language (iso639): eng,fre,ita,jpn..
  output_lang           output language (iso639): eng,fre,ita,jpn..

options:
  -h, --help            show this help message and exit
  -o, --output_folder OUTPUT_FOLDER
                        custom output folder for the .srt file(s)
  --demux [DEMUX]       automatically demux .srt from file(s) (default stream index is 0)
  --delete              delete the source .srt file after processing
```

**Translate a single subtitle**:

---

```bash
python srt-ai-translator.py INPUT.srt eng ita
```

**Translate all subtitles in a folder**:

```bash
python srt-ai-translator.py . eng ita
```

**Translate all subtitles auto-demuxing srt (stream index=0) in a folder**:

```bash
python srt-ai-translator.py . eng ita --demux 0
```

## Screen

![image](https://i.postimg.cc/VNx3gQmP/1.png)
