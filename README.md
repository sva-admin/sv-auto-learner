<p align="center"><a href="https://loop.sv-academy.org"><img src="https://raw.githubusercontent.com/sva-admin/claude-skills/main/assets/sv-academy-512.png" width="96" alt="Silicon Valley Academy"/></a></p>

# SV Auto Learner

**Watch once, keep the skill.** ดูครั้งเดียว ได้สกิลติดเครื่อง

A video becomes a skill for your business. Paste a YouTube link, a playlist or your own recording into Claude Code or Codex. The agent captures everything said and everything shown, merges them into one timeline it reads in full, writes notes and a one-page cheat sheet in Thai and English, then turns the method into a new skill for your own business, installs it, and proves it once on a real task. Audio and video never leave your computer: transcription runs locally, with no API key and no upload, and your AI provider sees only the transcript lines and contact sheets the agent reads, as with any chat. SV Academy's own skill, in **one file**: [`SKILL.md`](SKILL.md) holds the whole method, including the helper script, so Claude Code and Codex get exactly the same thing.

## Install

Paste this into Claude Code or Codex:

```text
Install the skill from https://github.com/sva-admin/sv-auto-learner, then get this computer ready for it.
```

```text
ติดตั้งสกิลจาก https://github.com/sva-admin/sv-auto-learner แล้วเตรียมเครื่องนี้ให้พร้อมใช้งาน
```

The agent saves the skill where it keeps skills (Claude Code: `~/.claude/skills/sv-auto-learner/`, or the `skills` folder inside `CLAUDE_CONFIG_DIR` if you run Claude Code with one per account; Codex: `~/.agents/skills/sv-auto-learner/`, and current Codex also reads `~/.codex/skills`, so either works), always from the release `v1.0.0`, so every laptop in a class reads the same file. Then it checks your computer and asks you one question before anything is downloaded: English only (about 2.7 GB in all) or English and Thai (about 5.8 GB). It installs everything, checked against the file, and shows you a PASS table. That is the only setup. From then on you paste a link and say what you want.

Any agent without skill support:

```text
Read https://raw.githubusercontent.com/sva-admin/sv-auto-learner/v1.0.0/SKILL.md and follow it for everything we do in this session. Then get this computer ready for it.
```

## Three ways in

| You have | Way | What the agent does |
| --- | --- | --- |
| A YouTube link (**Easiest**) | 1. From one video | Checks the licence first and shows you a study card. Captures every word and every screen into one pack, writes notes and a cheat sheet, asks you three questions about your business, then writes, installs and proves your new skill. Deletes the video. Tested end to end on a real Creative Commons YouTube video on 9 Oct 2026. |
| A playlist, or several links | 2. From a series | Lists every video with its length, licence and captions, and waits for your yes. Learns them one at a time, maps where they agree and where they differ, and makes one skill that credits every creator. Not yet tested (9 Oct 2026). |
| Your own recording (Zoom, Meet, a Mac or iPhone screen recording) | 3. From your recording | No download and no licence question. Turns a task you recorded once, with your voice over it, into a skill or a checklist your staff can follow. Your original file is never touched. |

From then on the three are the same: ask questions from the pack, fix the skill in words, and the creator is always credited.

**SV Auto Learner, SV Motion or SV Edits?** SV Auto Learner takes a video in and turns it into knowledge and a skill. [SV Motion](https://github.com/sva-admin/sv-motion) makes new video from words. [SV Edits](https://github.com/sva-admin/sv-edits) edits files you already have. A skill learned here hands its work to them: a sticker rule becomes a print-ready PSD through SV Edits, a hook method becomes an SV Motion beat list.

## Then, from the same pack

| Preset | Prompt |
| --- | --- |
| Learn one video | `Use SV Auto Learner to learn https://youtu.be/<id>. Give me notes and a cheat sheet in Thai and English, then ask me what skill I want from it.` |
| เรียนหนึ่งคลิป | `ใช้ SV Auto Learner เรียนคลิปนี้ https://youtu.be/<id> ขอโน้ตและชีตสรุปภาษาไทยกับอังกฤษ แล้วถามว่าอยากได้สกิลอะไร` |
| A playlist | `Use SV Auto Learner to learn this playlist, one video at a time, and make one skill from what they agree on.` |
| One chapter only | `Use SV Auto Learner on 12:00 to 24:00 of this video only.` |
| My own recording | `Turn my screen recording into a skill my staff can follow, and prove it on one real order.` |
| Just answer a question | `Use SV Auto Learner to answer this from the video, with timestamps, and make no skill: which settings does it use for export?` |
| Make it my skill | `Make a skill from this video's method for my product, in my brand's words.` |
| With SV Motion, SV Edits or SV Blender | `Make a skill from this video's hook method that writes SV Motion beat lists for my product.` |
| Fix the skill in words | `Add a check to my new skill: every price must come from my menu file.` |
| Update a skill with a new video | `Use SV Auto Learner to update my skill with what this new video adds, and prove it again.` |

## What it does

- **Nothing in the video is lost.** Speech comes from the uploader's captions when they exist, or from Whisper on your computer, with word-level timing, Thai included. Screens come from every scene change, and a slow screencast is caught by a frame every 4 s (2 s for your own recordings); ask for a denser pass on any range. On a talking-head video, frames that show only the presenter are thinned to one per 20 s of the same shot, so the contact sheets are about the slides and screens (on our test video: 107 frames kept instead of 218, every slide still there). Both merge into one transcript with every slide in place, and the agent looks at every contact sheet.
- **Honest transcripts.** Lines the model is unsure of are marked `[unclear]`, silence it might invent words over is marked `[inaudible]`, and the screen wins when a name is misheard. When Whisper gets stuck repeating a phrase, that stretch is transcribed again; if it still repeats, the repeats are cut, the line says so, and YouTube's own auto captions for those seconds sit beside it as a cross-check. Thai uses the accurate large model; the fast model on Thai is only ever a labelled draft.
- **Your skill, not a summary.** Three questions about your business, then a skill that does one real job for you: a Doer, a Checker for your existing work, or a Coach for skills that need hands. Every step cites the second of the video it came from.
- **Proved once.** A fresh agent that has only the new skill runs it on one small real task, and every check is pass or fail with the evidence shown to you.
- **Learn, never republish.** The licence is checked before any download. The video and audio are deleted once the pack is built, and the hand-over lists what was deleted. For a Standard-licence video, the transcript, kept frames and contact sheets go the next time SV Auto Learner runs after 7 days, or at once when you say so. Notes and skills are written in the agent's own words (a built-in check blocks copied runs of the transcript), and the creator is credited and linked in every file.
- **Safe skills.** Before a new skill is installed, a check blocks risky commands, keys and tokens, links you did not approve, and personal data such as phone numbers and LINE IDs.
- **Pinned and checked.** Every tool and model download is checked by SHA-256 against the file; Python packages are pinned to exact versions. No admin password, no Homebrew needed, no window ever opens.

## Requirements

A Mac (Apple Silicon for the fastest speech; Intel should work through faster-whisper, untested) or Windows 10 or 11 (untested as of 9 Oct 2026). A Windows laptop with Smart App Control on cannot run the tools: use a Mac or another laptop, and never turn Smart App Control off for this. Claude Code or Codex. An internet connection for the first install and for YouTube.

On disk: about 1.1 GB for the private Python and speech package on a Mac, about 40 MB for yt-dlp, and, only if your computer has none, about 170 MB for Deno and FFmpeg. Speech models: 1.6 GB for English, plus 3.1 GB for accurate Thai. A 720p copy of the video lives only while it is being read.

Before a class, at home, so the room's Wi-Fi does not have to carry it: run the install prompt, say yes to both models if you work in Thai, and try it once on a short Creative Commons video or a 30 second screen recording of your own.

How long it takes, measured on an M3 Max on 9 Oct 2026: the tools install in about 20 s and the speech package in about 20 s on a fast connection (the models take longer: 4.7 GB in all for Thai). A 7 minute 43 second English YouTube tutorial went from link to finished pack in under 3 minutes on a fresh setup with the skill's own tools (metadata 15 s, captions 18 s, download 21 s, then about 2 minutes for the timing sample, speech, frames and pack; the frame pass alone took 63 s with the pinned FFmpeg and 11 s with Homebrew's). A 44 second English screen recording became a finished pack in 50 s; a 33 second Thai one in 18 s with the accurate model (59 s the first time, while the 3 GB model loads). An hour of Thai speech takes about 18 to 51 minutes on the accurate model, so long videos run in the background while you keep working; captions, when the uploader made them, take seconds. An 8 GB laptop or a fanless MacBook Air is slower: one video at a time, a chapter for anything long, and the laptop plugged in with the lid open. After the first minute of speech, the estimate uses your own computer's measured speed. On Windows the speech runs on the processor (untested): expect about 2.5 hours for an hour of Thai.

## Rights, in plain words

- **Your own recordings** and **Creative Commons videos** are the two safe choices, and the ones used in class.
- For a video under the **Standard YouTube Licence**, the creator keeps all rights and YouTube's terms do not allow downloading unless YouTube or the creator permits it. SV Auto Learner asks you first, explains this, and offers a words-only option and a stop. The download and transcript are for your private study: the video and audio are deleted once the pack is built, and the transcript, kept frames and contact sheets the next time SV Auto Learner runs after 7 days, or at once when you say so. The new skill holds only the method, rewritten in new words with credit, and none of the creator's words, slides or images. You are responsible for having the right to study it.
- **Never**: private, members-only, paid, age-restricted or region-locked videos, cookies, passwords, VPNs or proxies. Nothing is re-uploaded, and no clip or frame is ever made for sharing.

## Release check

Every laptop installs from the release tag `v1.0.0`, and the helper's checksum lives inside `SKILL.md`, so a release is only ready when the tag URL serves this exact file. After pushing the tag:

1. `curl -fsSL https://raw.githubusercontent.com/sva-admin/sv-auto-learner/v1.0.0/SKILL.md -o /tmp/svl.md` returns the file, not a 404.
2. Extract the helper from it with the command in Pre-flight step 3 and compare its sha256 with the pin printed there. They must match.
3. Any later change to the helper needs a new pin and a new tag; the old tag stays as it was.

## License

MIT, for the SV Academy text and scripts in this repository, written in our own words. See [LICENSE](LICENSE).

The tools are run unmodified from their own releases and never redistributed here: [yt-dlp](https://github.com/yt-dlp/yt-dlp) (Unlicense; the standalone release binaries the helper downloads are GPLv3+), [FFmpeg](https://ffmpeg.org) (LGPL or GPL; on a Mac without one, the static builds from [ffmpeg-static](https://github.com/eugeneware/ffmpeg-static)), [Deno](https://github.com/denoland/deno) (MIT), [uv](https://github.com/astral-sh/uv) (MIT or Apache-2.0), [mlx-whisper](https://github.com/ml-explore/mlx-examples) and [faster-whisper](https://github.com/SYSTRAN/faster-whisper) (MIT), the Whisper weights and the mlx-community and Systran conversions (MIT), the turbo conversion for Windows and Intel Macs by Dropbox, formerly Mobius Labs ([dropbox-dash/faster-whisper-large-v3-turbo](https://huggingface.co/dropbox-dash/faster-whisper-large-v3-turbo)), and [Pillow](https://github.com/python-pillow/Pillow) (MIT-CMU).

Inspired by the [watch](https://github.com/bradautomates/claude-video) plugin by Bradley Bonanno (MIT): its silent setup check, its option-injection guard and its focus mode for a time range shaped ours. SV Auto Learner shares none of its code and, unlike it, never uploads audio to a cloud transcription service.

## More from Silicon Valley Academy

- All of our published skills: [github.com/sva-admin/claude-skills](https://github.com/sva-admin/claude-skills)
- Courses and free lessons: [sv-academy.org](https://sv-academy.org)
