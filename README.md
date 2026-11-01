# F26 live simulation

Read-only live viewer for the F26 humanoid. Camera orbit and zoom are available to visitors; checkpoint and simulation controls remain with the local Spark operator.

## Enable GitHub Pages once

Open https://github.com/Seungtae451/supermimic_f26/settings/pages and choose **Deploy from a branch**, branch **main**, folder **/(root)**, then **Save**.

Public site after deployment: https://seungtae451.github.io/supermimic_f26/

## Live service

This static page embeds the running Spark simulator. Spark, the simulator container, and the Cloudflare tunnel must remain running. It does not execute GPU simulation on GitHub and does not upload training checkpoints.

The current Quick Tunnel is temporary. If it restarts, update both the iframe source and direct link in index.html to the new public HTTPS URL. A permanent backend hostname requires a named tunnel/domain.
