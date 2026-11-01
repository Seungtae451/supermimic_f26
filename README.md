# F26 browser simulation

https://seungtae451.github.io/supermimic_f26/

Each browser runs the F26 policy, learned world model, and MuJoCo 3.16.0 in its own Web Worker. ONNX Runtime Web 1.31.1 uses single-threaded WASM; the renderer interpolates positions and quaternions and displays measured render FPS / simulation Hz. No per-frame server simulation or WebSocket stream is used by this version.

Published checkpoint: **11600**. All40 LAFAN1 retargeted motions are available as lazy downloads. Motion/reset/seek/pause/speed/policy/noise/friction/perturb controls are local to each browser. This is live computation, not prerecorded playback. The checkpoint menu describes the exported build; new training snapshots need export before they can run in-browser. Reload published build reloads exported assets, not a live training checkpoint.

Initial download is approximately100MB for models/runtimes/one motion, with versioned caching. Other motions download on selection. Assets currently come from the Spark HTTPS tunnel, so it must be online to load uncached files; once loaded, simulation runs in the visitor's browser. A tunnel restart changes its temporary hostname, requiring an index iframe/directlink update.

Original Cocelo coupling, torque clipping, action mapping and integration settings were preserved. Four native numerical fixtures and60-step/three-motion shipped-WASM core tests pass. ARM Node full step+three FK snapshots measured~5–6ms median; this is not a browser rendering FPS claim. Actual browser graphics performance depends on the visitor's device.

The previous Spark-streamed implementation remains at [server viewer](server.html). It has8 concurrent GPU sessions; that limit does not apply to the browser-local simulation.

This page embeds the static browser app; model exports are served by the running Spark asset server. Source backend training and raw checkpoints were not uploaded to this repository.
