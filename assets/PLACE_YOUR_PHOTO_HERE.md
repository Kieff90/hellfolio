# Photo Requirements

Place your profile photo in this folder with the filename `your-photo.jpg`.

## Specifications

- **Filename**: `your-photo.jpg`
- **Format**: JPEG or PNG (rename to `.jpg` either way)
- **Minimum size**: 400×400 pixels
- **Shape**: Will be displayed as a circle — use a square crop
- **Subject**: Your face should be centered and take up most of the frame
- **Background**: A plain or blurred background works best

## How it appears

The photo is displayed in the hero section with:
- Circular crop via `border-radius: 50%`
- Soft neon glow border
- Floating animation (subtle up/down motion)
- 3D tilt effect on mouse hover
- Parallax scroll on desktop

## Tips

- A professional headshot or clear portrait works best
- Avoid busy backgrounds — they will be partially visible through the circular crop
- Minimum 400px but 600–800px is ideal for retina displays
- The photo is displayed at `clamp(220px, 28vw, 380px)` wide on desktop
- On mobile it scales down to `clamp(80px, 24vw, 108px)`
