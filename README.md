# StudyStream

**🛠 Changelog: Optimization & Performance Update (v2.2)**
**Fixed Data Persistence**: Switched from fragile date strings to numeric Unix timestamps to prevent sessions from "vanishing" due to browser formatting.

**Targeted Deletion**: Added a DEL button for each entry by mapping unique Firebase IDs, allowing you to prune specific logs.

**Recalculation Logic:** Refactored calculateDailyTotal to filter by Year/Month/Day integers for 100% accurate daily resets.

**Performance Tuning**: Applied tabular-nums and will-change CSS to the timer to reduce CPU/GPU jitter during high-speed updates.

**Script Cleanup:** Eliminated duplicate const declarations and syntax typos that were blocking execution.

**Glitch Expansion**: Injected new symbols (Σ, Δ, ERR) into the title-glitch engine for a deeper cyber aesthetic.


**🛠 Changelog: Optimization & Performance Update (v2.1)**

**🚀 Performance Enhancements**
CPU Overhead Reduction: Eliminated "Layout Thrashing" by implementing DOM Caching. Reference pointers for displayEl, pauseBtn, and labelInput are now stored on initialization instead of being queried 60 times per second.

**Render Throttling**: Added a String-Diffing Guard in the main loop. The browser now skips the expensive "Paint" and "Composite" steps if the timer's centiseconds haven't actually changed.

**Hardware Acceleration**: Forced GPU Compositing for the background grid using translateZ(0) and backface-visibility: hidden. This offloads the 3D perspective math from the CPU to the Mac's GPU.

**Memory Management:** Replaced high-frequency setInterval scrolling with a stochastic (randomized) setTimeout glitch effect for the document title, significantly reducing "Idle Wake Ups."

**🎨 UI/UX Improvements**
**Aesthetic Glitch Title:**_Implemented a randomized title scrambler using Cyberpunk-themed characters (Ø, Σ, ▓) for a more "system-authentic" feel.

**GPU-Optimized Shadows**: Simplified expensive text-shadow layers to a single high-performance glow, reducing the complexity of every frame redraw.

**Responsive Scaling:** Integrated clamp() and vmin units for the timer display to ensure a seamless "always-on-top" experience across different window sizes.

**🔧 Logic & Stability**
Synchronized Timing: Migrated to requestAnimationFrame (rAF) for the main timer loop, ensuring the UI refreshes in perfect sync with the monitor's refresh rate (Hz).

Firebase Integrity: Maintained real-time cloud synchronization for the DAILY_TOTAL and SYSTEM_LOG while keeping the main thread lean
