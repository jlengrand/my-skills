# video-to-skills

A Claude Code skill that extracts reusable skill files from educational video content. Point it at a YouTube URL or a local transcript file, and it identifies the teachable frameworks inside, then writes structured `.md` skill files you can invoke in future Claude Code sessions.

## Requirements

### yt-dlp (required for YouTube mode)

Install via Homebrew:
```bash
brew install yt-dlp
```

Or via pip:
```bash
pip install yt-dlp
```

Verify it's working:
```bash
yt-dlp --version
```

yt-dlp is only needed when providing a YouTube URL. If you're supplying a local transcript file, no additional tools are required.

## Usage

Invoke the skill by name in Claude Code, then describe what you want:

```
/video-to-skills
```

---

### Extract all skills from a YouTube video

```
/video-to-skills

https://www.youtube.com/watch?v=tLJR5OaiCw
```

Claude fetches the auto-generated captions, identifies skill candidates, presents them for your approval, then writes each approved skill to `skills/<skill-name>/skill.md`.

---

### Extract skills from only part of a YouTube video (by topic)

```
/video-to-skills

https://www.youtube.com/watch?v=tLJR5OaiCw — only the landing page section
```

Claude fetches the full transcript but narrows its analysis to the section that matches "landing page". Only skill candidates from that portion are surfaced.

---

### Extract skills from only part of a YouTube video (by timestamp)

```
/video-to-skills

https://www.youtube.com/watch?v=tLJR5OaiCw — only the topic at minute 4
```

Claude filters the VTT transcript to the content around that timestamp and extracts skills from there only.

---

### Extract all skills from a local transcript file

```
/video-to-skills

/path/to/my-transcript.vtt
```

Claude reads the file at that path, infers source metadata from the filename or content, and proceeds with extraction. If the source can't be determined, it will ask before continuing.

---

### Extract skills from a specific section of a local transcript

```
/video-to-skills

/path/to/my-transcript.txt — only the business model part
```

Same as above, but Claude restricts analysis to the section matching "business model".

---

### Review and improve existing skill files

```
/video-to-skills

Please review the skills in skills/ and flag any quality issues.
```

Claude checks each skill file against the quality criteria (frontmatter, source attribution, modes of operation, output format) and proposes fixes.

---

## Output

Skills are written to:
```
skills/
  <skill-name>/
    skill.md
```

Each file contains a role declaration, the core framework, modes of operation, output format, and a source attribution block crediting the original creator.

## Notes

- Not every idea in a video becomes a skill. Claude filters out pure storytelling, sponsor content, and highly tool-specific advice that won't generalize.
- If a YouTube video has no auto-generated captions, Claude will tell you and suggest providing a transcript manually.
- Source attribution is always included — it's non-negotiable.
