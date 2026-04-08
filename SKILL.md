---
name: live-scene-commentator
description: Opens the camera and provides pseudo real-time scene descriptions by capturing a frame every second.
---

# Live Scene Commentator

## Instructions

This skill opens the camera UI and periodically captures a still image to describe the current scene.


### When to use
Use this skill when the user says things like:
- "カメラで今写ってるものを説明して"
- "周りに何が見えるか教えて"
- "リアルタイムっぽく説明して"
- "カメラを開いてシーンを説明して"

### Action
When the user asks to start the camera description mode, call the `run_js` tool with:
- **script name**: `index.html`
- **data**: a JSON string with these fields:
  - `action`: `"start"`
  - `intervalMs`: Number (optional, default `1000`)
  - `language`: String (optional, default `"ja"`)
  - `style`: String (optional, default `"concise"`)
  - `focus`: String (optional, default `"overall"`)

### Optional stop action
If the user asks to stop the camera description, call `run_js` with:
- **script name**: `index.html`
- **data**:
  - `action`: `"stop"`

### Optional single-shot action
If the user asks for just one explanation from the current camera view, call `run_js` with:
- **script name**: `index.html`
- **data**:
  - `action`: `"single"`
  - `language`: `"ja"`
  - `style`: `"concise"`
  - `focus`: `"overall"`
