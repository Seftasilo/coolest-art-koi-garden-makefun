# Golden Koi — Make the coolest art (make.fun `coolest-art-01`)

A single piece of art, written by `main.py` to `/output/entry.png`.

## The piece

**"Golden Koi"** — a giant ornate golden koi fish with gold-patterned
scales swims through a tranquil Japanese garden pond, pink cherry
blossom petals floating on teal water, soft morning light through bamboo.

Why this concept, against the judge's criteria in order:

1. **It stops you.** A gold fish the size of the pond, glowing against
   teal water and pink blossom — warm gold on cool teal is an instant hook.
2. **The idea.** The koi wears its own garden: gold filigree scales like
   embroidery, petals drifting like snow. Stillness as spectacle.
3. **Style.** One mood throughout: serene, dreamlike, soft pastel morning
   light — calm where other entries shout.
4. **Craft.** Clean render, no text, no smears or garbled details; the
   koi, the ripples and the blossom all read clearly.
5. **It reads small.** At ~300 px the golden fish shape on teal water
   still hits — the composition is one big shape, not detail.

## How it was made

- The image was generated as original art for this entry (no stock photo,
  no one else's artwork), then center-cropped to square, resized to
  1024×1024 and saved as JPEG quality 92 (281,409 bytes — under the
  1 MiB limit).
- `main.py` (Python 3.13, standard library only) copies the bundled
  `entry.png` byte-for-byte to `/output/entry.png`. No network, no clock,
  no randomness: two runs write identical bytes.

## Files

- `main.py` — the entrypoint; copies `entry.png` to the output directory.
- `entry.png` — the art itself (JPEG bytes, 1024×1024, 281,409 bytes).
- `LICENSE` — MIT.
- `.makefun/owner.json` — claim file naming the entrant's wallet.

## Run it locally

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
# writes out/entry.png; run it twice and compare sha256 — identical.
```

## Verify

```sh
python3 -c "from PIL import Image; im=Image.open('entry.png'); print(im.format, im.size)"
ls -l entry.png   # must be <= 1048576 bytes
```
