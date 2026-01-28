# 🌐 Next.js: Handling Media Errors & Async Playback

Today, I debugged specific frontend issues related to audio/video playback and resource loading within a **Next.js 16 (Turbopack)** environment.

### 🛠️ Error 1: AbortError (The play() request was interrupted)
* **The Problem:** This occurs when a `pause()` is called before the `play()` promise has resolved. In fast-paced React environments, rapid state changes can trigger this race condition.
* **The Solution:** Implemented a check to ensure the `play()` promise is handled correctly:
  ```javascript
  const playPromise = audioRef.current.play();
  if (playPromise !== undefined) {
    playPromise.then(() => {
      // Automatic playback started!
    }).catch(error => {
      // Auto-play was prevented or interrupted
    });
  }

 ### 🛠️ Error 2: NotSupportedError (No supported source found)
* **The Problem:** The browser fails to load the media because the source path is invalid or the network request was blocked.
* **The Solution:** Verified static asset paths and checked environment variables to ensure the source URL is correctly constructed for the Turbopack build.

### 💡 Insight
Asynchronous UI updates in modern frameworks require careful management of browser-level APIs. Using **Promises** to handle media states prevents unhandled console exceptions and significantly improves the overall user experience.
