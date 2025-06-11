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

## Usage

**Help**:

```bash
python srt-ai-translator.py -h
```

**Translation** _(Available languages: [ISO 639-2 Codes](https://www.loc.gov/standards/iso639-2/php/code_list.php))_:

```bash
python srt-ai-translator.py INPUT.srt eng ita
python srt-ai-translator.py . eng ita
```

## Screen

![image](https://i.postimg.cc/VNx3gQmP/1.png)
