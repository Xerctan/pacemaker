# instabox-pacemaker

A five-minute heartbeat for one instabox machine, because instabox pauses a sandbox
after 30 minutes idle and offers no way to switch that off.

Why it has to live outside the machine: a paused sandbox runs nothing, so nothing on
the box can wake itself, and a visit to its public URL does not wake it either (it
answers 503 and stays suspended). Only the API can, so something on the outside has to
call it.

This repository is public on purpose: scheduled workflows in public repositories do
not consume the 2,000 monthly GitHub Actions minutes a private one gets, which is what
lets it run every five minutes. The only thing in here is the workflow; the machine's
key is held as the repository secret `INSTABOX_API_KEY` and is never printed.

The same poke runs, more slowly, from the private vault repo
(`raffyfatlly/claude`, `.github/workflows/pacemaker.yml`) as a backstop.
