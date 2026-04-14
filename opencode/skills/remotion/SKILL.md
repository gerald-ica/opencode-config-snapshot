---
name: remotion
description: Use when the task involves programmatic video creation with React using Remotion, including video composition, rendering, and timeline-driven media workflows.
---

# Remotion - Programmatic Video Creation with React

## What is Remotion?
Remotion is a framework for creating videos programmatically using React.

- **Repository:** https://github.com/remotion-dev/remotion
- **Docs:** https://remotion.dev/docs
- **Stars:** 33.8k

## Quick Start

```bash
# Create new project
npx create-video@latest

# Start preview
cd my-video
npm install
npm run dev

# Render video
npx remotion render src/index.ts MyComposition out/video.mp4
```

## Key Concepts

### Composition
A video is defined as a React component with frames:

```tsx
import { useCurrentFrame, useVideoConfig, AbsoluteFill } from 'remotion';

export const MyVideo: React.FC = () => {
  const frame = useCurrentFrame();
  const { fps, durationInFrames, width, height } = useVideoConfig();
  
  return (
    <AbsoluteFill style={{ backgroundColor: 'white' }}>
      <h1 style={{ fontSize: 100 }}>Frame {frame}</h1>
    </AbsoluteFill>
  );
};
```

### Register Composition
```tsx
import { Composition } from 'remotion';

export const RemotionRoot: React.FC = () => {
  return (
    <Composition
      id="MyVideo"
      component={MyVideo}
      durationInFrames={150}
      fps={30}
      width={1920}
      height={1080}
    />
  );
};
```

## Essential Components

- `<AbsoluteFill>` - Full-frame container
- `<Sequence>` - Timing sequences
- `<Audio>` - Audio tracks
- `<Video>` - Video embeds
- `<Img>` - Images with loading handling
- `<OffthreadVideo>` - Performance-optimized video

## Essential Hooks

- `useCurrentFrame()` - Current frame number
- `useVideoConfig()` - fps, duration, dimensions
- `interpolate()` - Animate values over frames
- `spring()` - Physics-based animations

## Animation Example

```tsx
import { useCurrentFrame, interpolate, spring, useVideoConfig } from 'remotion';

export const AnimatedText: React.FC = () => {
  const frame = useCurrentFrame();
  const { fps } = useVideoConfig();
  
  // Linear interpolation
  const opacity = interpolate(frame, [0, 30], [0, 1]);
  
  // Spring animation
  const scale = spring({
    frame,
    fps,
    config: { damping: 10, stiffness: 100 }
  });
  
  return (
    <h1 style={{ 
      opacity, 
      transform: `scale(${scale})` 
    }}>
      Hello World
    </h1>
  );
};
```

## Rendering

```bash
# Render MP4
npx remotion render src/index.ts MyComposition out/video.mp4

# Render with props
npx remotion render src/index.ts MyComposition out/video.mp4 --props='{"title": "Hello"}'

# Render GIF
npx remotion render src/index.ts MyComposition out/video.gif

# Render frames as PNG
npx remotion render src/index.ts MyComposition out/frames --image-format=png
```

## With TailwindCSS

```tsx
// tailwind.config.js is supported
<AbsoluteFill className="bg-gradient-to-r from-purple-500 to-pink-500 flex items-center justify-center">
  <h1 className="text-6xl font-bold text-white">TailwindCSS Works!</h1>
</AbsoluteFill>
```

## Lambda Rendering (Cloud)

```bash
# Deploy to AWS Lambda
npx remotion lambda sites create src/index.ts

# Render in cloud
npx remotion lambda render <site-id> MyComposition
```

## Best Practices

1. **Use `staticFile()`** for assets in the public folder
2. **Use `delayRender()`** for async data loading
3. **Use `<OffthreadVideo>`** for better performance with video files
4. **Keep compositions pure** - same frame = same output
5. **Use `calculateMetadata()`** for dynamic duration

## Claude Code Integration

Remotion has official Claude Code support. When working on Remotion projects:

1. Install skills: `npx skills add remotion-dev/skills`
2. Use Blank template with TailwindCSS for AI prompting
3. The AI can modify React components and render videos

## Common Patterns

### Dynamic Text
```tsx
const text = "Hello World";
const frame = useCurrentFrame();
const charsShown = Math.floor(frame / 2);
return <h1>{text.slice(0, charsShown)}</h1>;
```

### Staggered Animation
```tsx
{items.map((item, i) => (
  <Sequence from={i * 15} key={i}>
    <FadeIn>{item}</FadeIn>
  </Sequence>
))}
```

### Audio Sync
```tsx
import { Audio, Sequence } from 'remotion';
import music from './music.mp3';

<>
  <Audio src={music} />
  <Sequence from={30}><TextAppears /></Sequence>
</>
```
