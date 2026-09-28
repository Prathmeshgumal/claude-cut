# Reference edit: "Pune — Brand New Day"

2026-09-28 · Analysed by sampling frames (1 per second, plus closer looks at key moments) and analysing the audio, the same way claude-cut's import analysis works.

A 38.7-second city montage styled like a film's opening credits, inspired by the end credits of *Spider-Man: Brand New Day*. It is the quality bar for claude-cut's edits.

**Format:** 16:9 (1276×718), 24 fps, 15 shots, all joined by hard cuts. Music only, no speech.

## Shot list

| Time (s) | Length (beats at 144 BPM) | Shot | On-screen text |
| --- | --- | --- | --- |
| 0.0–1.9 | about 4.5 | Bridge pylon against the sky, locked off | PUNE / BRAND NEW DAY |
| 1.9–5.3 | 8 | Covered walkway, symmetrical, centred | Inspired by the movie from / MARVEL STUDIOS |
| 5.3–7.8 | 6 | Heritage building with traffic passing | Produced by / MY LIL POCKET |
| 7.8–11.1 | 8 | Woman from behind (soft focus), metro train passing | Directed by / NINAD KONDE |
| 11.1–14.4 | 8 | Bridge arches against the sky | Featuring / STREETS OF PUNE |
| 14.4–17.0 | 6 | High view of a tree-lined road with traffic | And / TRAFFIC |
| 17.0–19.5 | 6 | Pedestrians crossing a road | PEDESTRIANS (people walk in front of the text) |
| 19.5–22.8 | 8 | Book seller arranging books | SELLERS |
| 22.8–26.1 | 8 | Two friends on a bench, traffic blurred behind | AND FRIENDS |
| 26.1–28.6 | 6 | Street seen through a gap between pillars | Shot entirely on / SONY ZVE10-M2 |
| 28.6–30.3 | 4 | Balloon seller | Director of photography / NINAD KONDE |
| 30.3–31.9 | 4 | Flowers at a stall | Production designer / AASTHA |
| 31.9–33.6 | 4 | Stall owner reading | Music by / STEVE LACY |
| 33.6–35.2 | 4 | Tree and building in silhouette | And / TRAFFIC NOISES |
| 35.2–38.7 | held to the end | Glowing balloons at night | A SHUTTERHEX PRODUCTION |

## What makes it work

1. **Every cut lands on the beat.** At 144 BPM, all 14 cuts are within about 50 ms of a beat (one frame at 24 fps is 42 ms).
2. **The rhythm builds.** Shots last 8 or 6 beats, then 4 beats each from 28.6 s, so the ending speeds up before the final shot is held.
3. **Film-credit typography.** A small, widely letter-spaced label above a bold, spaced name, in one clean sans-serif. The text appears and disappears with the cut, with no animation.
4. **Text placed in empty space.** Each credit sits in the calm part of its frame (sky, road, a dark corner), and the position changes from shot to shot.
5. **Text behind people.** In the PEDESTRIANS shot a man walks in front of the word, which needs a moving mask of the person.
6. **One consistent look.** Warm tones and slightly lifted shadows on every shot.
7. **Cinematic footage.** Tripod shots, careful composition, shallow depth of field, framing through foreground objects, and motion blur from a slow shutter. These come from filming, not editing.

## What we learned for the design

- **The beat detector picked the wrong tempo at first.** Standard beat tracking reported 96 BPM, and the cuts were up to 370 ms off it. The second candidate, 144 BPM, matched every cut. The design now keeps several tempo candidates, shows the grid, and lets you switch or tap the tempo (design.md section 14.2).
- **Credit titles and text placement** become a graphics component with automatic placement suggestions (design.md section 16).
- **Text behind people** needs person masks for chosen shots (design.md section 16.3).
- **A consistent look** needs per-clip colour matching, not only one LUT (design.md section 17).
- **Footage quality matters as much as editing.** A shot report during import flags shaky, dark or blurry clips and suggests stabilizing them (design.md section 9).

## Can claude-cut match it?

| Feature | Possible? |
| --- | --- |
| Hard cuts on the beat, with a speeding-up pattern | Yes |
| Film-credit text, placed in empty space | Yes; placement is suggested, and you can adjust it |
| Text behind moving people | Yes, for chosen shots; hair and fast motion can need manual touch-up |
| Consistent colour grade | Yes |
| Film grain | Yes |
| Motion blur | Partly; it can be added to chosen clips, but looks best when filmed |
| Tripod-steady, cinematic shots | Partly; stabilization and slow digital push-ins help, but composition and depth of field come from filming |

**Test plan:** re-create this edit from its 15 shots with claude-cut, then compare cut timing (within 1 frame of the beat), text placement and look.
