# Stickman RPG Adventure 2 — Optimized v0.7.0

An **unpacked, version-control-friendly source snapshot** of the optimized Scratch 3 project *Stickman RPG Adventure 2 (v0.7.0)*.

> **Status:** The game's story is unfinished in this version. This snapshot concentrates on reducing Scratch's serialized code size; no new gameplay features have been added. A complete interactive playthrough has **not** been performed on the optimized build.

## What is in this repository?

| Path | Description |
| --- | --- |
| `project.json` | Optimized Scratch project data, including blocks, scripts, variables, lists, and sprites. |
| `assets/` | **Every** referenced sprite costume, backdrop, and sound from the optimized `.sb3`. |
| `tools/build_sb3.py` | Rebuilds a playable/importable `.sb3` file. |
| `tools/check_project.py` | Checks project structure and referenced asset files. |
| `tools/optimize_scratch_sb3.py` | Optimization utility used to transform original Scratch archives. |
| `.github/workflows/build.yml` | Validates and builds a downloadable Scratch project on GitHub Actions. |
| `docs/` | Project layout, optimization notes, and publishing instructions. |

## Build the Scratch project

Install **Python 3.9+**. No external Python packages are required.

```bash
python tools/check_project.py
python tools/build_sb3.py
```

The output is `dist/Stickman_RPG_Adventure_2_v0.7.0_Optimized.sb3`. Open [Scratch](https://scratch.mit.edu/projects/editor/), choose **File → Load from your computer**, and select the `.sb3` file.

If you don't have Python, the GitHub Actions workflow builds the `.sb3` when you push changes. On the GitHub repository, open **Actions → Build Scratch project → latest successful run → Artifacts**, then download its artifact ZIP.

## About the optimization

The optimized snapshot shortens opaque Scratch identifiers and removes redundant serialized defaults. All original block records and media files are intended to be preserved. The optimized `project.json` is smaller than the original (approximately 2.91 MB versus 5.17 MB). Some Scratch editor versions can restore omitted defaults on save; recheck file size after editing.

**Important:** Static structural checks do not prove the game runs correctly. Test saved games, dialogue, battles, UI, and the Scratch editor import/export cycle.

## Versioning approach

Edit or generate `project.json` and `assets/`, commit those files, and build a fresh `.sb3`. The `dist/` folder is deliberately ignored, since it would duplicate tens of megabytes of media already tracked in the repository.

## Credits and rights

The game's internal story text credits **Poukatchu** as the original creator. Please preserve creator attribution and verify permission to **redistribute the entire project publicly**, including its images, music, and other assets. This repository does **not** include an open-source license, because no license or redistribution authorization was supplied. Public availability on GitHub does not itself grant reuse rights.
