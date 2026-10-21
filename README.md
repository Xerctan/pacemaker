# instabox-pacemaker

This repository is public on purpose: scheduled workflows in public repositories do
not consume the 2,000 monthly GitHub Actions minutes a private one gets, which is what
lets it run every five minutes. The only thing in here is the workflow; the machine's
key is held as the repository secret `INSTABOX_API_KEY` and is never printed.
