# How I Used Claude Cowork to Turn Years of Buried Zoom Recordings into a Searchable Personal Knowledge Archive

If you've recorded Zoom sessions locally for years, you probably have a folder you never open.


My partner is a professional astrologer who's been doing independent study on and off with a master astrologer for three and a half years, 60 to 90 minutes each. She'd recorded all 62 of them to her Mac hard drive – Not using cloud recording, not using AI transcription. For months, she's been asking me if I could help her organize these and make it easier for her to locate videos that touched on certain topics. Years of professional continuing education, sitting there doing nothing.

[Zoom's AI Companion](https://www.zoom.com/en/ai-assistant/) only works on cloud recordings made after you've enabled it, and it searches within a single recording, not across your whole archive. And it does nothing to help with the pile of Zoom videos sitting on your hard drive.

I've spent the last couple of months becoming a power user of Claude [Cowork](https://claude.ai/download), And yesterday it hit me that it would be the perfect tool to tackle this task. Even though this is not founder or enterprise work, it's a great example of the power of Cowork and the creative and iterative collaboration that can lead you to a great solution quickly. And I got to add a couple of powerful AI web APIs to my arsenal. Let's dive in. 

---
![<# alt text #>](../../../../Library/Application%20Support/CleanShot/media/media_EiZAj6vEOZ/CleanShot%202026-03-12%20at%2017.29.30.png "Screenshot")
[IMAGE: Archive UI — full-width hero screenshot]

---

## The starting point

To extract topics, summaries, and useful categories from the videos, I first needed to get full transcripts. But the Zoom folder on the Mac had none, just raw video and audio. I knew I could run [OpenAI's Whisper model](https://github.com/openai/whisper) on my Mac to transcribe audio files, so I got that all set up. Whisper is free and open source, and you can install it on Mac using Homebrew (an essential tool for any builder on Mac). 

Cowork walked me through exactly what to install, and wrote shell scripts to loop through all 61 meeting folders and run whisper on the audio files. After some setup I fired off the script and sat back. I thought my M1 Macbook Pro was powerful but pretty soon it became apparent that transcribing 60+ hours of video would tie it up for more than 40 hours, more time than I wanted to spend. (Not to mention it made the fans sound like a hoverboat). I wondered whether there was a faster web-based service and asked Claude.

The alternative was [Groq's API](https://console.groq.com/docs/speech-to-text), which runs the same Whisper model in the cloud at 216x real-time. (Note the spelling – not Grok). With Cowork helping me at every step, 5 minutes later I had my account, my API key, and Cowork (again) wrote a script to loop through all the audio files and pipe them through Groq API for transcription. (footnote: Groq has a maximum file size of 25 MB for audio chunks. Many of my audio files were bigger than this. Cowork's script automatically split larger files into chunks and handled shipping them off to Grok. In small enough pieces, getting the individual transcripts back and stitching them all together. I never needed to write or debug the script, and it all worked perfectly. ) Once I fired off the script, the entire archive of 60+ hours of audio processed in under 10 minutes. Total Groq API cost: $2.32. I can live with that. 

Now is a good time to pause and think about data privacy. Your audio and video recordings, depending on your professional realm, may be privileged or subject to a statutory privacy regime such as HIPAA or attorney-client privilege. Groq's terms state that data sent in API requests aren't retained by default, with a Zero Data Retention option available. I judge that this policy was adequate for this purpose – personal study sessions, But it is potentially *not** adequate for privileged clinical or legal content. Knowing where your material sits on that spectrum is a judgment call you need to make before you start. If you frequently have a lot of local audio or video to process through this type of model, buying a powerful machine that you control, such as a Mac Studio or a powerful Mac Mini, may make more sense. 

The final result was a transcript.txt file in every single video folder, along with a .vtt file, which is a standardized format that adds second-by-second time stamps. With the full transcripts in place, I had the raw material I needed to build the organizer my partner needed.  

---

## Building the Archive Browser 

With 62 transcripts in place, I gave Cowork a structured brief: read everything, rename the folders to descriptive titles, summarize each session, build a taxonomy (Fancy name for categorization tags ) from the transcripts, apply tags, log every change before making it, and build an index.

The taxonomy is where things got interesting. I didn't tell Cowork what the tags should be. I asked it to read the full corpus and figure that out. The first pass came back with a flat list of 24 tags across all 61 sessions — a reasonable first draft, but too coarse to be useful. "Pluto" and "Saturn" are single tags sitting alongside "Shadow Work" and "Relationships." You can't do much with that.

So I pushed Cowork to go back through all the transcripts and make a much more granular category system. But in over 60 hours of in-depth technical lectures, if we just had a flat list of topics mentioned, there would be hundreds of items and it would become unwieldy. So we talked about what the tags actually needed to do to be useful. A quick back and forth with Cowork Surfaced.  something I had known about in a previous life but forgotten: faceted taxonomy terms. We landed on this structure: 6 dimensions, 78 tags total. Planets & Bodies (16 tags), Zodiac Signs (12), Houses (12), Aspects & Geometry (10), Techniques (11), and Themes (17 life-domain categories). Cowork then re-tagged all 61 sessions against the new schema.

These tools have gotten so good so fast that it's easy to overlook. At every iterative turn, when I asked it to enhance a feature, we would settle on a course of action and it would just go do it. It completely rebuilt the HTML page and all the logic; worked flawlessly every time. I have a decades-old background in these technologies, but even when I was most up to speed on them, this is at least 5x the speed I could work out, maybe 10x. 

Faceted structure means you can filter by Planet + House + Theme simultaneously and actually locate something.

![<# alt text #>](../../../../Library/Application%20Support/CleanShot/media/media_0F8Bdclmtp/CleanShot%202026-03-12%20at%2014.33.51.png "Screenshot")
[IMAGE: Faceted sidebar screenshot — tight crop, left panel only]

The index itself went through several rounds. The first pass had 3–5 sentence summaries per session – useful for card previews, but not enough for a real reference. I had Cowork regenerate them at 500–1000 words each, with a separate short teaser for the browsing interface.

The final index has a full-text search field, a faceted sidebar with tag counts that update as you filter, and a card grid showing each session with date, title, teaser, and tags. Clicking a card expands it inline: full summary, a timestamped outline pulled from the VTT file, a link to the raw transcript, and an embedded video player with navigable timestamps. Filter logic uses union within a facet and intersection across them, so you can narrow by multiple dimensions at once.

[IMAGE: Napkin hexagon diagram — filter logic visualization]

![<# alt text #>](../../../../Downloads/Taxonomy%20-%20visual%20selection.png "Taxonomy - visual selection.png")
[CAPTION: Selecting Pluto (53 sessions), then 12th House, then Psychology narrows progressively. Adding a second planet within the same facet widens results back out.]

The whole index with browse, search, and filtering is a single self-contained HTML file. No server, no login, no internet connection required.

---

## Panache and polish – adding evoactive visuals

This was working genuinely well and very useful, but though the UI was polished, it looked like a business application. There was no imagery at all. Astrology is rich in mythology and metaphor, and I knew it would be more appealing for my partner to use this as an ongoing resource if the visuals expressed that as well. And since we had full text transcripts of each discussion, I knew we had the raw material to make some wonderful imagery. 

I had an idea of the look I wanted – copperplate engraving style, rotating through 4 duotone palettes. This grounds the imagery in historical or ancient and metaphorical style, while the vivid color brings it into the realm of current and future imagination. It had been a while since I had played much with AI image generation, so I needed to quickly get up to speed on current capabilities. Cowork helped me decide which models to use and pointed me to FAL.AI, a developer-focused platform for rapid image generation that lets you use hundreds of different models with significant control at very good prices. After some back and forth, it seemed like the Flux 2 model was the one that would perform well for me. 

Similar to Groq, in five minutes I had signed up, added $5 of funds with my credit card, and got my API key for Cowork to use. 

I uploaded reference images and we went back and forth until Cowork had the prompt vocabulary right. From there it wrote a prompt generator that read each session's content and produced an image description tied to the specific planets, signs, and themes discussed, then wrote a batch script to generate all 62 images through [fal.ai's Flux 2](https://fal.ai/models/fal-ai/flux/dev) API, with resume support so an interrupted run could pick up where it left off.

I fired off the script a rem without error, And generated 62 images in about 90 seconds. Total cost: 80 cents. I'm a very visual person, and when I saw these rich, evocative thumbnails added to the UI, I got genuinely excited. Together, Cowork and I are creating a thing that's beautiful as well as useful! (This is a far cry from two years ago, where it took five minutes to watch a couple of images render, and they were laughably bad. It seems like ten years of progress in a year or two.) And I still have all the scripts that Cowork wrote, so if I ever want to change all the image styles at once, it would only take about 20 minutes to have a conversation about the different style I wanted, have it rewrite all the prompts, even choose a different model, and get a whole new set of images. 


![<# alt text #>](../../../../Library/Application%20Support/CleanShot/media/media_zOrNcD6Q3c/CleanShot%202026-03-12%20at%2018.01.33.png "Screenshot")
[IMAGE: Thumbnail grid — tight crop showing duotone palette variations]

---

## Problem solved!

Without having to research and buy custom software, which would probably cost more than we wanted to spend (and be at best a marginal solution to the problem), my partner now has a customized tool that she can access whenever she needs to. It helps keep all those hours invested in learning and conversation fresh and usable. She can search three and a half years of astrological study by planet, house, technique, or life theme. She can find every session where a specific topic came up, read a detailed summary, and jump to the relevant moment in the recording. The archive went from a folder she never opened to a working professional reference.

Total time with Cowork: one afternoon.

The same result is available to anyone sitting on an undifferentiated pile of recorded knowledge – coaches, counselors, music teachers, therapists, researchers, anyone who records sessions and lets them accumulate. The recording is already done. If you are lacking transcriptions, now that costs almost nothing and takes almost no time. The organizational work that used to take weeks is now a well-structured conversation with Cowork and a few scripts you run once.

---

## Get the plugin

I'm packaging everything here – the transcription pipeline, the taxonomy generator, the index builder, the thumbnail batch script, and the prompt templates – as a free Cowork plugin. Point it at your recordings folder, answer a few questions about your domain, and it builds the archive.

When it's ready, I'll post it here. [CTA: replace this line with your follow/subscribe/notify mechanism before publishing]











