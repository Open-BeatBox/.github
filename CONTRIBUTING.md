# Contributing to Open-BEATBox

Thanks for wanting to help. Open-BEATBox is a research platform built to be reproduced, modified and improved by other labs, so build reports and corrections from people who actually assembled one are as valuable as code.

This guide covers every Open-BEATBox repository. Individual repositories may add their own notes on top of it.

## Pick the right repository

The project is split by layer, so contributions go to the repository that owns the material:

| What you want to change | Repository |
| --- | --- |
| Assembly steps, part references, the master BOM | [assembly-tutorials](https://github.com/Open-BeatBox/assembly-tutorials) |
| Manual pages, protocols, technical notes | [Open-BeatBox_Documentation](https://github.com/Open-BeatBox/Open-BeatBox_Documentation) |
| CAD, enclosure, PCB, mechanical design | [Open-BeatBox_Hardware](https://github.com/Open-BeatBox/Open-BeatBox_Hardware) |
| Firmware and embedded control | [Open-BeatBox_firmware](https://github.com/Open-BeatBox/Open-BeatBox_firmware) |
| GUI, acquisition, analysis tools | [Open-BeatBox_Software](https://github.com/Open-BeatBox/Open-BeatBox_Software) |
| The website and its build pipeline | [Open-BeatBox.github.io](https://github.com/Open-BeatBox/Open-BeatBox.github.io) |

If you are not sure, open the issue anywhere and we will move it.

## Before you start

**For anything beyond a typo, open an issue first.** A short description of the problem saves you from building something we have already solved differently, and it gives other labs a place to say "we hit that too".

**Ask questions in [Discussions](https://github.com/Open-BeatBox/Open-BeatBox.github.io/discussions)**, not issues. Build help, "is this normal?", parts sourcing and task-design questions all belong there. Issues are for defects and concrete proposals.

## What is especially useful

Because this is hardware that other people physically build, some contributions are worth more than code:

- **Build reports.** What went wrong, on which module, at which step, and what you did about it. Include your hardware revision.
- **Part substitutions that worked.** Suppliers differ by country and parts go out of stock. Tell us what you used instead.
- **Validation data.** Evidence that a module behaves as documented, or does not.
- **Corrections to the assembly steps.** If an instruction was ambiguous at the bench, it is a bug.
- **Protocol templates** for tasks you have run.

## Reporting a problem

Use the issue templates — they ask for the things we always end up asking for anyway. Whatever the template, the three details that matter most are:

1. **Which module and which hardware revision** (V2, V3).
2. **What you expected versus what happened.**
3. **Where exactly** — the guide page and step number, or the file and line.

Photographs help enormously for mechanical and wiring problems.

## Pull requests

1. Fork the repository and branch from `main`.
2. Keep each pull request to one concern. A PR that fixes a wiring diagram and refactors the GUI is two PRs.
3. Describe what you changed and why. If it is a bench correction, say what you observed.
4. For the website and software repositories, run the checks before pushing:
   ```bash
   npm run type-check
   npm run test
   npm run build
   ```
5. For documentation, confirm the manual still builds without warnings:
   ```bash
   pip install -r requirements.txt
   python -m sphinx -b html source _build/html
   ```

Some repositories use Git submodules. Clone with `--recurse-submodules`, and note that a submodule pointer change is a real change that needs review like any other.

### Documentation conventions

Assembly documentation follows the naming and structure rules in [conventions.md](https://github.com/Open-BeatBox/assembly-tutorials/blob/main/conventions.md). Match the surrounding style rather than introducing a new one.

## Licensing and provenance

Open-BEATBox uses layer-specific open licences, so a contribution is licensed under the terms of the repository it lands in:

| Layer | Licence |
| --- | --- |
| Hardware | CERN-OHL-S-2.0 |
| Firmware | GPL-3.0 |
| Software and website | AGPL-3.0 |
| Documentation | CC-BY-4.0 |

By opening a pull request you confirm you have the right to contribute the material and are doing so under that repository's licence. If you are contributing work owned by an employer or institution, check first.

**Do not commit third-party CAD, datasheets or figures** unless the licence permits redistribution. Link to them instead.

## Credit

Contributors are credited in the project credits and, for substantive contributions, in the citation metadata. If you have contributed and are not listed, that is an oversight — open an issue.

## Code of Conduct

Participation is covered by our [Code of Conduct](CODE_OF_CONDUCT.md). Report concerns to [eric.burguiere@cnrs.fr](mailto:eric.burguiere@cnrs.fr).
