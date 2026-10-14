# Awesome-AI-Video-Watermark-Remover

# Top AI Video Watermark Remover Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Video Inpainting, Temporal Consistency & Watermark Removal*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **AI Video Watermark Removal**. These tools erase logos, timestamps, and branding overlays from video footage—using inpainting, motion tracking, and temporal propagation to reconstruct the underlying pixels naturally across frames.

**Examples** include HitPaw Video Watermark Remover, VEED.IO, Media.io, 123Apps, Topaz Video AI, Apowersoft, Runway, Kapwing, Wondershare Filmora, and Video Watermark Remover Online (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, LaMa-based inpainting, and flow-guided video restoration—ideal for video engineers, archivists, and developers seeking transparent, vendor-independent watermark removal.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[HitPaw Video Watermark Remover](https://www.hitpaw.com/watermark-remover.html)**  
  AI-powered watermark removal for video and images. Offers five removal modes: AI Model, Matte Filling, Color Filling, Smooth Filling, and Gaussian Blur. 2025 version added motion prediction algorithms for dynamic watermarks. Supports batch processing (up to 50 videos) and 4K export. Free online version limited to 500 MB with HitPaw branding; paid removes restrictions .

- **[VEED.IO](https://www.veed.io/tools/remove-watermark-from-video)**  
  Browser-based video editor with watermark removal via cropping, overlays, stickers, text, and shapes. Not true inpainting—covers or crops the watermark rather than reconstructing pixels underneath .

- **[Media.io](https://www.media.io/)**  
  Browser-based video watermark remover handling MP4/MOV. Free tier processes short clips with decent quality for static watermarks on clean backgrounds. Motion backgrounds show smearing. Export limits push toward paid tiers .

- **[123Apps (Online Video Cutter)](https://online-video-cutter.com/id/remove-logo)**  
  Free browser-based tool allowing users to select watermark area and delete with one click. Supports wide variety of codecs and formats .

- **[Topaz Video AI](https://www.topazlabs.com/topaz-video-ai)**  
  Video enhancement application (upscaling, denoising, interpolation, stabilization). Trial exports carry visible Topaz watermark. Watermark cannot be removed after purchase—users must re-export from original footage with a licensed version .

- **[Apowersoft Video Watermark Remover](https://www.apowersoft.com/watermark-remover)**  
  Desktop tool for removing watermarks from images and videos. Features batch processing and multi-format support. Video editor also supports splitting, merging, cropping, rotating, GIF conversion, and audio extraction .

- **[Runway](https://runwayml.com/)**  
  Cloud-based AI video platform with inpainting and generative editing. Can remove watermarks as part of broader AI video workflows.

- **[Kapwing](https://www.kapwing.com/)**  
  Online video editor with watermark removal via cropping or overlays. Exported videos from free tier carry a Kapwing watermark in the bottom 10% of the frame .

- **[Wondershare Filmora](https://filmora.wondershare.com/)**  
  Consumer video editor. Free trial exports carry Filmora watermark. Official removal methods: log in with Wondershare ID for trial access, or use the "Refer a Friend" program to earn watermark-free export days .

- **[Video Watermark Remover Online](https://www.videowatermarkremover.com/)**  
  Web-based tool for removing watermarks from videos. Simple upload, select, and process workflow.

## Open-Source GitHub Projects

- **[WatermarkRemover-AI (D-Ogi)](https://github.com/D-Ogi/WatermarkRemover-AI)**  
  AI-powered watermark removal using **Florence-2** (Microsoft) for detection and **LaMA** for inpainting. Specifically designed for AI-generated videos like Sora, Sora 2, and Runway . Features: **Smart Detection** via Florence-2, **Seamless Removal** via LaMA inpainting, **Video Support** with two-pass detection and audio preservation, **Batch Processing** for entire folders, **Preview Mode** to verify detection before processing, **Fade In/Out Handling** extending masks for fading watermarks, **GPU Acceleration** (CUDA), **Multi-Language UI** (English, French, Chinese, Japanese, Portuguese, etc.), and multiple UI themes. Cross-platform (Windows portable .exe, Linux/macOS shell scripts). FFmpeg optional for audio preservation .

- **[static-ghost](https://www.npmjs.com/package/static-ghost)**  
  Open-source tool for removing **static watermarks** from videos using LaMa inpainting via IOPaint . Pipeline: Input video → Extract frames (FFmpeg) → Crop watermark region (multiprocess) → LaMa inpaint (IOPaint) → Paste back (multiprocess) → Reassemble video (FFmpeg). **Crop-and-paste optimization** processes only the watermark region (10–15× fewer pixels than full frames), making a 10-minute 1080p video processable in ~2 hours on CPU instead of 20+. Features: browser-based region picker (`static-ghost pick`), direct coordinate specification (`--region x,y,w,h`), auto-detection via multi-frame differencing (`static-ghost detect`), mask dilation control (5–15px for logos), Apple Metal GPU acceleration (~2× faster), and configurable detection sensitivity. CLI and Python API. Performance benchmarks: 30 sec video ~8 min CPU / ~4 min MPS; 10 min ~2.5 hr CPU / ~1.5 hr MPS .

- **[ffmpeg-video-watermark-remover-v2](https://github.com/OzzyLennon/ffmpeg-video-watermark-remover-v2)**  
  Lightweight, **zero-cost** video watermark removal using `ffmpeg delogo` filter . Works **entirely offline**—no API keys, no cloud services, no AI models. Supports **fixed-position** watermarks (single delogo pass) and **dynamically-moving** watermarks (auto-segmentation + multi-pass delogo + concat). Pipeline: Sample frames → Analyze with vision model → Segment if moving → Apply delogo → Merge → Verify with vision model. **Limitations**: delogo fills regions with blurred pixels—works best on simple/static backgrounds. Semi-transparent watermarks and complex AI-generated watermarks may still show traces. For natural content-aware fill, a different pipeline (AI inpainting) is needed .

- **[Kapwing-Logo-Remover (P4R1H)](https://github.com/P4R1H/Kapwing-Logo-Remover)**  
  Discord bot that removes Kapwing watermarks by **automatically cropping 10% from the bottom** of images, videos, and GIFs . Note: Kapwing watermarks are positioned in the bottom 10% of exported media. Users must add 10% padding at the bottom during export to ensure the watermark is fully removed by cropping. Supports `.png`, `.jpg`, `.jpeg`, `.mp4`, `.mov`, `.avi`, `.gif`. Requirements: Python 3.x, `py-cord`, `moviepy`, `Pillow`, `dotenv`. Simple `/cropmedia` command workflow .

- **[ProPainter](https://github.com/sczhou/ProPainter)**  
  ICCV 2023 video inpainting framework (6,079 GitHub stars) . Improves propagation and transformer for video inpainting. State-of-the-art results in video object removal. Foundation for advanced watermark removal pipelines requiring temporal consistency. VapourSynth filter available (`dan64/vs-propainter`) for integration into video processing workflows .

- **[E2FGVI](https://github.com/MCG-NKU/E2FGVI)**  
  **End-to-End Framework for Flow-Guided Video Inpainting** (CVPR 2022) . Features **flow-guided feature propagation** with deformable convolution, **temporal focal transformer** for long-range spatial-temporal dependencies, and **end-to-end trainable architecture**. Processes 432×240 videos at 0.12 seconds per frame on Titan Xp GPU—**15× faster** than previous flow-based methods. Achieves state-of-the-art accuracy on PSNR, SSIM, VFID, and temporal consistency metrics. Strong baseline for video inpainting research .

- **[Inpaint-Anything (geekyutao)](https://github.com/geekyutao/Inpaint-Anything)**  
  Unified framework for inpainting using Segment Anything (SAM) and inpainting models . **Remove Anything Video** feature: click on an object in the first frame, and it's removed from the whole video. Pipeline: SAM segments object → Tracking model (OSTrack) follows it → SAM segments each frame → Video inpainting model (STTN) fills removed regions. Supports LaMa and STTN backends. Requires SAM checkpoint (sam_vit_h_4b8939.pth) and STTN checkpoint (sttn.pth) .

- **[STTN](https://github.com/researchmm/STTN)**  
  ECCV 2020: **Learning Joint Spatial-Temporal Transformations for Video Inpainting** (505 GitHub stars) . Joint spatial-temporal transformer for video inpainting. Used as the inpainting backend in Inpaint-Anything's Remove Anything Video pipeline .

### Additional Strong Open-Source Options

- **[IOPaint](https://github.com/Sanster/IOPaint)** — The inpainting engine behind static-ghost and many watermark removal tools. Supports LaMa, MAT, FcF, and other SOTA models.
- **[LaMa](https://github.com/advimman/lama)** — Resolution-robust large mask inpainting model from Samsung AI. Foundation model for static watermark removal.
- **[Florence-2](https://huggingface.co/microsoft/Florence-2-large)** — Microsoft's vision foundation model used for watermark detection in WatermarkRemover-AI.
- **[FFmpeg delogo filter](https://ffmpeg.org/ffmpeg-filters.html#delogo)** — Built-in FFmpeg filter for watermark removal via blurred pixel fill.
- **[VapourSynth](https://github.com/vapoursynth/vapoursynth)** — Video processing framework supporting ProPainter and other inpainting filters.
- Community **n8n** workflows for batch watermark removal pipelines and quality gating.

**Frameworks for building custom systems**: Combine **WatermarkRemover-AI** for AI-powered detection and inpainting with **static-ghost** for efficient crop-and-paste static watermark removal, **ProPainter** or **E2FGVI** for temporally consistent video inpainting, **ffmpeg-video-watermark-remover-v2** for zero-cost fixed/dynamic watermark removal, and **Inpaint-Anything** for interactive object removal—creating a fully self-hosted, enterprise-grade video watermark removal platform.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- **Watermark removal may violate copyright law, terms of service, or attribution requirements.** Many stock video sites, AI generators, and content platforms prohibit removing watermarks from their content. Use these tools only on videos you own or have explicit rights to modify.
- **Moving watermarks are genuinely hard.** Free and basic tools rarely handle motion-tracking algorithms needed for moving watermarks—expect smearing, ghosting, or faint traces . ProPainter and E2FGVI are designed for this but require GPU resources and technical setup.
- **Complex backgrounds fail.** Watermarks over faces, text, or fast-moving content tend to leave blur patches or mismatched reconstruction. Basic tools can introduce artifacts even when AI-based software minimizes quality loss .
- **"Watermark removal" means different things.** VEED and Kapwing use cropping or overlays—they cover the watermark rather than reconstruct pixels underneath . ffmpeg delogo fills regions with blurred pixels—best on simple/static backgrounds . AI inpainting (LaMa, ProPainter) generates plausible content but may drift on complex scenes.
- **Trial watermarks are locked to the tool.** Topaz Video AI trial watermarks cannot be removed after purchase—users must re-export from original footage with a licensed version . Filmora and HitPaw offer official free-tier removal methods (login, referral programs) .
- Self-hosted open-source solutions require proper GPU provisioning for neural models, FFmpeg installation for audio preservation, and ongoing maintenance. Always test on short clips before committing to full video processing .

---

**Made for video editors, archivists, content creators, and developers building transparent video watermark removal solutions.**  
Let's make AI Video Watermark Removal more open, data-driven, and temporally consistent.
