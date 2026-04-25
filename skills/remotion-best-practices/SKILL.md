---
name: remotion-best-practices
description: "Programmatic video generation with React using Remotion. Use when creating video content, animated demos, pitch videos, product teasers, social media videos, or any programmatic animation."
visibility: public
requires_body_cleanup: true
---
# Remotion — Vidéo Programmatique React

## Setup
```bash
npx create-video@latest
cd my-video
npm run dev    # Preview in browser
npm run build  # Render to MP4
```

## Core Concepts
```tsx
import { useCurrentFrame, useVideoConfig, interpolate, spring, AbsoluteFill } from 'remotion'

// Composition = video template
export const MyVideo = () => {
  const frame = useCurrentFrame()          // current frame (0 → durationInFrames)
  const { fps, durationInFrames, width, height } = useVideoConfig()

  // Smooth animation between values
  const opacity = interpolate(frame, [0, 30], [0, 1], {
    extrapolateLeft: 'clamp',
    extrapolateRight: 'clamp'
  })

  // Physics-based spring animation
  const scale = spring({ frame, fps, config: { damping: 200 } })

  return (
    <AbsoluteFill style={{ backgroundColor: '#1B4332' }}>
      <div style={{ opacity, transform: `scale(${scale})` }}>
        COLHYBRI
      </div>
    </AbsoluteFill>
  )
}

// Register composition
registerRoot(() => (
  <Composition
    id="MyVideo"
    component={MyVideo}
    durationInFrames={150}  // 5 seconds at 30fps
    fps={30}
    width={1920}
    height={1080}
  />
))
```

## Key APIs
- `interpolate(frame, [in], [out])` — value animation
- `spring({ frame, fps })` — physics animation
- `<Sequence from={30}>` — delay a section by 30 frames
- `<Audio src={} />` — add audio track
- `<Video src={} />` — embed video
- `<Img src={} />` — image (use instead of `<img>`)

## Render Commands
```bash
npx remotion render src/index.ts CompositionId out.mp4
npx remotion render src/index.ts CompositionId out.mp4 --codec=gif  # GIF for LinkedIn
npx remotion render src/index.ts CompositionId out.mp4 --scale=0.5  # Half resolution
```

## Rules
- Always define width, height, fps, durationInFrames explicitly
- Use `interpolate` with clamp extrapolation to avoid runaway values
- Test in browser preview before rendering (saves time)
- Render in CI/CD for consistent output (not local machine)
- 30fps for web, 24fps for cinematic feel
