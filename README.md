# gist.id profile

This is your gist.id profile — a directory of markdown files describing
who you are professionally. The gist.id builder turns these files into a
signed, verifiable artefact rendered at `gist.id/<your-handle>`.

## Quickstart

1. **Use this template** to create your own profile repository in your
   GitHub account. The new repo can be named anything (`profile`,
   `gist-id-profile`, your handle, etc.) — only the contents matter.

2. **Add the `gist-id` topic** to your new repository (Settings → top of
   the page → topics). This is how the network discovers you.

3. **Enable GitHub Pages**: Settings → Pages → Source: GitHub Actions.
   The build workflow handles deployment automatically.

4. **Edit the markdown files** to describe yourself. The Ada Renström
   example content is a guide — replace it with your own.

5. **Optionally import from LinkedIn**: download your LinkedIn data
   archive (Account → Settings → Get a copy of your data), then run the
   importer locally:
   ```
   cargo install gist-id-builder
   gist-id import path/to/Basic_LinkedInDataExport.zip
   ```
   Or wait for the importer to be available as a one-click GitHub Action
   (post-MVP).

6. **Push to main**. The build runs automatically. Your profile appears
   at `gist.id/<your-github-username>` within a few minutes.

## What the files mean

| Path | What lives there |
| --- | --- |
| `profile.md` | Your name, headline, bio, contact info |
| `resume/work.md` | Work experience |
| `resume/education.md` | Education |
| `resume/skills.md` | Skills (load-bearing — drives discovery) |
| `resume/projects.md` | Notable projects |
| `resume/patents.md` | Patents |
| `posts/` | Optional individual posts |

Optional resume sections (add files as needed):
`certificates.md`, `awards.md`, `publications.md`, `volunteer.md`,
`languages.md`.

The full layout spec is at
[gist-id/gist-id/docs/layout.md](https://github.com/gist-id/gist-id/blob/main/docs/layout.md).

## What gets verified

Your `resume/skills.md` claims are cross-referenced against your public
GitHub activity at build time — language bytes, repo significance, package
authorship. Skills with strong evidence rank higher in network discovery;
unverified skills are still shown but flagged.

You don't need to do anything special to enable this. The build runs in
your GitHub Actions environment and queries the same public APIs anyone
else could query.

## Privacy

Your profile repository is public. Everything in it — every file, every
commit — is visible to anyone who can find it. The system has no concept
of private profile data; if you don't want it published, don't put it in
this repo.

The importer deliberately skips private categories from LinkedIn exports
(messages, connections, inferred data, etc.). Only publishable data
becomes part of your profile.

## Licence

This template repository is dual-licensed under MIT and Apache 2.0 (see
`LICENSE-CODE`). Your content (the markdown files you write in your fork)
is published under the licence in `LICENSE-CONTENT` — by default,
CC BY-NC-SA 4.0 with an additional clause prohibiting use for AI model
training. You can change this in your own fork if you prefer different
terms.

## Learn more

- [gist.id](https://gist.id) — the product
- [github.com/gist-id/gist-id](https://github.com/gist-id/gist-id) — protocol and tooling source
