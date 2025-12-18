# Sora 2 Video Generation Prompting

> Advanced techniques for OpenAI Sora 2 video generation

## Video Extension Technique

### Sora Extend Method

A three-step approach to extend Sora 2 videos beyond the native limits:

1. **Prompt Segmentation**
   - Break initial prompt into smaller, coherent segments
   - Create contextual bridges between sections
   - Maintain narrative continuity

2. **Sequential Generation**
   - Generate each segment independently
   - Capture final frame of each clip
   - Feed final frame into subsequent generation

3. **Concatenation**
   - Automatically join video segments
   - Create continuous output
   - Maintain visual consistency

### Implementation

```python
# Conceptual workflow
def extend_sora_video(prompt, duration_seconds):
    segments = segment_prompt(prompt, duration_seconds)
    clips = []
    last_frame = None

    for segment in segments:
        clip = generate_sora_clip(
            prompt=segment,
            init_frame=last_frame
        )
        clips.append(clip)
        last_frame = extract_final_frame(clip)

    return concatenate_clips(clips)
```

## Prompt Engineering Tips

### Structure
```
[SCENE DESCRIPTION]
[CAMERA MOVEMENT]
[LIGHTING/MOOD]
[STYLE REFERENCE]
[DURATION NOTES]
```

### Example Prompt
```
A cinematic drone shot ascending through morning fog
over ancient Japanese temples, golden hour lighting
with warm amber tones, slow upward camera movement
revealing mountains in the distance, Studio Ghibli
aesthetic with photorealistic textures
```

### Key Elements

1. **Specificity**: Detail every visual element
2. **Camera Language**: Use cinematic terminology
3. **Temporal Flow**: Describe motion and progression
4. **Style Anchors**: Reference known visual styles
5. **Technical Specs**: Resolution, aspect ratio, duration

## Resources

- [mshumer/sora-extend](https://github.com/mshumer/sora-extend) - Extension notebook
- [OpenAI Cookbook](https://cookbook.openai.com) - Official guides
- [shijincai/sora-prompt-generator](https://github.com/shijincai/sora-prompt-generator)
