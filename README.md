# F26 browser simulation

https://seungtae451.github.io/supermimic_f26/

Each browser runs the F26 policy, learned world model, and MuJoCo3.16.0 in its own WebWorker. ONNXRuntimeWeb1.31.1 uses single-threadedWASM; renderer interpolates poses and displays measuredrenderFPS/simulationHz. No per-frame server simulation or WebSocketstream is used.

## Automatic checkpoint updates

The Spark deployment service checks for completed numbered checkpoints every30seconds and publishes every 2,000 training iterations (12000, 14000, 16000, etc.; only versions newer than the currently published build are eligible). CPU export, nativeONNXparity, all40motionhashchecks and shippedWASM/worker tests must pass before an atomic manifest switch. Failure keeps the previous published build and retriesafter5minutes. Training and PD settings are not changed; GPU is not requested by the deployment service.

The URL stays the same. Reload the page or use the published-build reload button to load a newly published version. A running browser does not swap models midway through a motion. The page header shows the actual loaded checkpoint. Export/verification can take additional time after a milestone. Numerical validation does not imply the policy has learned better balance.

All40 LAFAN1retargeted motions load lazily. Motion/reset/seek/pause/speed/policy/noise/friction/perturb controls remain local to each browser. This is live computation, not prerecordedplayback.

Initial download is approximately100MB, with versionedcaching; othermotions downloadonselection. SparkHTTPS tunnel serves staticassets and must stay online for uncacheddownloads. Once loaded, computation runs in the visitor's browser. A temporarytunnel restart changes hostname; update index iframe/directlink then.

OriginalCocelo coupling,torqueclipping,actionmapping andintegration settings preserved. Native fixtures/actualWASMworker tests pass. ARMNode step+3FK~5–6ms median is not a browserFPSclaim; devicecapabilities determineactualspeed.

Previous Sparkstreamed viewer: [server.html](server.html), limitedto8 concurrentGPUsessions. Thatlimit doesnotapply tobrowserlocalexecution. GitHub onlyembeds thestaticapp; rawtrainingcheckpoints/sourcebackendare not uploaded here.
