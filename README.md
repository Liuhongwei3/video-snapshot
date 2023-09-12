> Get snapshots from a video file in the browser

# Demo
[https://zzarcon.github.io/video-snapshot](https://zzarcon.github.io/video-snapshot)

# Install

```
$ yarn add video-snapshot
```

# Usage

```javascript
import VideoSnapshot from 'video-snapshot';

document.querySelector('input[type="file"]').addEventListener('change', onChange);

const onChange = async (e) => {
  const snapshoter = new VideoSnapshot(e.target.files[0]);
  const previewSrc = await snapshoter.takeSnapshot();
  const img = document.createElement('img');

  img.src = previewSrc;

  document.body.appendChild(img);
};
```

# Api

```typescript
type CustomVideoTime = 'start' | 'middle' | 'end';
type VideoTime = number | CustomVideoTime;

class VideoSnapshot {
  constructor(blob: Blob) {};
  takeSnapshot(time?: VideoTime): Promise<string>;
  end(): void;
}
```
