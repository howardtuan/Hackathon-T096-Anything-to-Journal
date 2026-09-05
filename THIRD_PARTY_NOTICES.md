# Third-party notices / 第三方來源與授權

This file records the software and services that Anything to Journal can interoperate with. No third-party executable, publisher class, bibliography style, logo, font, model weight, dataset, or user research content is vendored in this repository.

本檔記錄 Anything to Journal 可能搭配的軟體與服務。本儲存庫沒有內嵌第三方可執行檔、出版社 class／bibliography style、第三方標誌、字型、模型權重、資料集或使用者研究內容。

## Pre-existing work disclosure / 賽前既有內容揭露

The submission is based on the team's pre-existing open-source project, [howardtuan/Anything-to-Journal](https://github.com/howardtuan/Anything-to-Journal), and was not built from scratch during BUILDMODE GEN-AI HACKATHON 2026. The canonical project's public Git history records its initial commit on 2026-08-14 and version 1.1.0 on 2026-08-20. This competition-specific repository was created on 2026-09-05 to collect the submitted version, documentation, and subsequent submission history.

本參賽作品以團隊先前建立的開源專案 [howardtuan/Anything-to-Journal](https://github.com/howardtuan/Anything-to-Journal) 為基礎，並非在 BUILDMODE GEN-AI HACKATHON 2026 期間從零開始。原始專案公開 Git 紀錄顯示初始 commit 日期為 2026-08-14，v1.1.0 日期為 2026-08-20；本次比賽專用儲存庫建立於 2026-09-05，用於彙整參賽版本、說明與後續提交紀錄。

## Required runtimes / 必要執行環境

These runtimes are installed separately by the user and are not redistributed here.

| Project | Role | Upstream source and license |
| --- | --- | --- |
| Python 3.10+ | Core scripts, hashing, OOXML inspection, build, audit, packaging, local server | [Python](https://www.python.org/) — [PSF license stack](https://docs.python.org/3/license.html) |
| Node.js 18+ | `npx` installer and installer tests | [Node.js](https://nodejs.org/) — [Node.js license and bundled notices](https://github.com/nodejs/node/blob/main/LICENSE) |

The npm package declares no third-party package dependencies. The Python core workflow uses the standard library; `pypdf` is only an optional page-count fallback.

## Document toolchain / 文件工具鏈

All entries below are separately installed, optional except for one usable TeX engine, and retain their upstream licenses.

| Project | Role | Upstream source and license |
| --- | --- | --- |
| Tectonic | Preferred TeX engine | [Tectonic](https://tectonic-typesetting.github.io/) — [MIT](https://github.com/tectonic-typesetting/tectonic/blob/master/LICENSE) |
| TeX Live | Alternative TeX distribution and package collection | [TeX Live](https://tug.org/texlive/) — [per-component copying conditions](https://tug.org/texlive/copying.html) |
| XeLaTeX, pdfLaTeX, latexmk and BibTeX | Alternative compilation commands | Supplied by the user's TeX distribution; licenses are recorded by that distribution |
| Pandoc | Optional rich DOCX semantic conversion | [Pandoc](https://pandoc.org/) — [GPL-2.0-or-later](https://github.com/jgm/pandoc/blob/main/COPYING.md) |
| pypdf | Optional PDF page-count fallback | [pypdf](https://pypdf.readthedocs.io/) — [BSD-3-Clause](https://github.com/py-pdf/pypdf/blob/main/LICENSE) |
| Poppler | Optional PDF rendering and page inspection (`pdftoppm`, `pdfinfo`) | [Poppler](https://poppler.freedesktop.org/) — [upstream COPYING files](https://gitlab.freedesktop.org/poppler/poppler/-/tree/master?ref_type=heads) |
| LibreOffice | Optional native Office rendering and inspection | [LibreOffice](https://www.libreoffice.org/) — [MPL-2.0 and component notices](https://www.libreoffice.org/about-us/licenses/) |
| Inkscape | Optional vector conversion | [Inkscape](https://inkscape.org/) — [GPL-2.0-or-later](https://inkscape.org/about/license/) |
| ImageMagick | Optional raster conversion | [ImageMagick](https://imagemagick.org/) — [ImageMagick License](https://imagemagick.org/license/) |

The generic LaTeX profile checks for the following separately installed files: `article.cls`, `geometry.sty`, `iftex.sty`, `amsmath.sty`, `amssymb.sty`, `booktabs.sty`, `graphicx.sty`, `longtable.sty`, `tabularx.sty`, `threeparttable.sty`, `array.sty`, `siunitx.sty`, `natbib.sty`, `unsrtnat.bst`, `microtype.sty`, `setspace.sty`, `lineno.sty`, `caption.sty`, `subcaption.sty`, `indentfirst.sty`, `placeins.sty`, `adjustbox.sty`, `xurl.sty`, `hyperref.sty`, and engine-specific font packages. Each package remains subject to the license recorded in its [CTAN](https://ctan.org/) metadata and the installed TeX distribution.

When the user selects an Elsevier target, the workflow may interoperate with a user-supplied [`elsarticle`](https://ctan.org/pkg/elsarticle) class. It is not bundled here and is licensed under LPPL 1.3.

## External services and AI / 外部服務與 AI

| Service | Role | Terms / boundary |
| --- | --- | --- |
| OpenAI Codex or another compatible Agent runtime | Loads the skill and performs semantic source review and drafting with the user-selected model | No model weights, API client, API key, or model identifier is embedded. Use is governed by the selected provider and account terms; see [OpenAI Service Terms](https://openai.com/policies/service-terms/) when using Codex. |
| Overleaf | Optional destination for the generated `overleaf-upload.zip` | [Overleaf terms](https://www.overleaf.com/legal); the project never uploads or submits on the user's behalf. |
| Cloudflare Workers | Hosts the optional [project presentation website](https://hackathon-t096-anything-to-journal-website.howardtuan.workers.dev/) | [Cloudflare terms](https://www.cloudflare.com/terms/); the core skill does not depend on this website at runtime. |

The local Manuscript Workspace itself binds only to `127.0.0.1`, uses no external CDN, and does not upload manuscript content. Whether source materials are sent to a model depends on the Agent runtime selected and configured by the user.

## Data, templates, and generated content / 資料、模板與生成內容

- User source materials, extracted figures and tables, generated manuscripts, and submission files retain the rights and restrictions applicable to their original content.
- Publisher templates, journal instructions, classes, bibliography styles, fonts, and trademarks remain the property of their respective rights holders. Users must supply or retrieve them under applicable terms.
- Reference-manager exports and datasets are user inputs, not bundled project data.
- Repository-owned code, documentation, the generic LaTeX template, and `assets/logo.svg` are first-party work released under the repository [MIT License](LICENSE).

Installing or using a separate dependency or service does not relicense it under this project's MIT License. Users remain responsible for permissions, privacy, authorship, ethics, disclosure, and final submission decisions.
