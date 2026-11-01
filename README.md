# F26 live simulation

Each browser tab gets its own simulation session on Spark. Visitors can independently select checkpoints and motions, reset, seek, pause, change speed, and adjust controls without changing other sessions. Checkpoint refresh and latest loading affect only that session. Reloading or reconnecting starts a fresh session.

Public site: https://seungtae451.github.io/supermimic_f26/

The page embeds the Spark live simulator. Spark, the simulator container, and the Cloudflare tunnel must remain running. GPU simulation runs on Spark, not GitHub or visitors' machines. At most8 simultaneous physics sessions are admitted while training is running; additional connections retry when a session becomes free. Sessions are released when disconnected.

The current Quick Tunnel is temporary. If it restarts, update both iframe source and direct link in index.html to the new public HTTPS URL. For a permanent backend hostname use a named tunnel/domain.

GitHub Pages source: main / root. Only the static viewer page is published; training code and checkpoints are not uploaded.
