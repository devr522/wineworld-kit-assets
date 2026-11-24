Wine World character-kit 3D assets
==================================

This folder is the payload for a public HTTPS host. The Base44 app
loads every GLB, texture, HDR, clip, and portrait from:

  {ASSET_BASE}base_body.glb
  {ASSET_BASE}clothing_tshirt.glb
  {ASSET_BASE}tex/...
  ...

ASSET_BASE must end in a slash. The recommended production URL is a
commit-pinned jsDelivr URL, the same pattern live already uses for the
Mixamo Joe/Sophie models:

  https://cdn.jsdelivr.net/gh/<owner>/<repo>@<commit-sha>/assets/

Do not point production at @main. jsDelivr caches aggressively; pin a
SHA so a later asset fix is a deliberate URL bump in
src/lib/avatar/kit/assetBase.js.

What this folder contains
-------------------------
- assets/  CC0 MakeHuman / MPFB body, clothes, and hair GLBs; Poly Haven
  CC0 textures and HDR; animation JSON; barollo.png portrait.
- LICENSES.md and LICENSE_AUDIT.json  (CC0-1.0 assets, MIT kit code;
  commercial-resale audit PASS). Kit runtime code is NOT in this
  bundle; it is pasted into the Base44 app separately.

Nothing has been pushed. The box has no GitHub login (`gh auth status`
is logged out; the GitHub MCP connector needs auth). Do not create a
new account from this box.

What we need from Devin before a push
-------------------------------------
1. Which GitHub account should own the public repo?
2. Repo name. Suggestion: `wineworld-kit-assets` (public, assets and
   licenses only, no app secrets, no Git LFS).
3. Permission to run `gh auth login` on this box under that account,
   or Devin pushes this folder himself.

After the repo exists and a commit is pushed, set ASSET_BASE_DEFAULT
in src/lib/avatar/kit/assetBase.js to the pinned jsDelivr URL, then
paste that one-line change to Base44 (Preview only).

Layout reminder
---------------
  README.md
  LICENSES.md
  LICENSE_AUDIT.json
  assets/base_body.glb
  assets/clothing_*.glb
  assets/hair_*.glb
  assets/tex/*.jpg
  assets/env/warm_studio_1k.hdr
  assets/animations/*.json
  assets/barollo.png
  ...
