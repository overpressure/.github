# Governance

**TL;DR.** Each headset has a team that runs its own repository, its own layer branch in
[overpressure/linux](https://github.com/overpressure/linux) and its own folders in
[overpressure/packages](https://github.com/overpressure/packages). The `core` team owns what every headset
shares. A change needs a review where it touches shared code (CODEOWNERS), not where only one headset is
affected. Each team tags only its own releases.

## Teams

| Team | Who | Role |
| --- | --- | --- |
| Owners | the organization's owner | everything; the only ones who create repositories and teams and change the organization's settings |
| `core` | maintainers of the shared parts | *maintain* on overpressure, builder, matrix and .github; *write* on packages, linux and each headset's repository |
| `soc-<soc>` (`soc-sm8250`) | people porting headsets on that SoC | *write* on packages and linux; owns the SoC's layer |
| `<codename>` (`phoenix`) | one headset's maintainers | *maintain* on overpressure/&lt;codename&gt;; *write* on packages and linux; owns the headset's layer and folders |
| `triage` | helpers who sort issues | *triage* on every repository: labels, assignees, closing; no code |

Roles go to teams, not to single people.

## Reviews

Every default branch and layer branch takes pull requests only, with a green `ci`, and never a force push.
On top of that:

| Where | Who has to approve |
| --- | --- |
| overpressure, builder, matrix, .github | one review by `core` (code owner of everything) |
| packages | one review by the code owner of each changed path: `core` for the shared parts, the headset's team or `core` for `phoenix/` and `headsets/phoenix/`, `soc-sm8250` or `core` for `sm8250/` |
| a headset's repository (overpressure/phoenix) | nobody for the headset's own files; `core` for `.github/` and `headset.json` |
| linux `common/7.2` | one review by `core`; only `core` merges |
| linux `<soc>/7.2`, `<codename>/7.2` | only that layer's team merges, without a review count |

A team that may merge into a linux layer branch merges past that rule: in the web page *Merge without waiting
for requirements (bypass rules)*, on the command line `gh pr merge --merge --admin`. It skips only that rule;
the green `ci` stays required. Layer pull requests are opened by the Layers workflow and merged by a person.

While `core` has one member, the owners may merge their own pull requests without the review (by pull request
only, the green `ci` stays required). Once `core` has two, every shared change gets the other's review.

## Releases

| Tags | Who |
| --- | --- |
| overpressure `v*`, builder `YYYY.MM.DD*` | `core` |
| overpressure/&lt;codename&gt; `v*` | that headset's team |
| linux `<codename>/7.2-N` | that headset's team, only its own prefix; other tags `core` |
| packages | anyone with write access, by the release workflow: *Actions*, *Packages*, *Run workflow* on `main` with one line on what it brings. It picks the next date tag itself; a tag pushed by hand releases nothing. A release changes no headset until that headset moves its pin. |

No released tag moves or disappears.

## The organization

- Two-factor authentication for every member.
- Only owners create repositories and teams.
- Actions: GitHub's own and those listed in the organization's settings (astral-sh/setup-uv,
  lycheeverse/lychee-action), pinned by commit. Workflows get a read-only token by default; they may open pull
  requests (the Layers workflow does). Fork pull requests from first-time contributors wait for approval.
- One secret: the access token of Goggles, the project's bot on Matrix, in overpressure/matrix's environment
  `matrix`, which only that repository's workflows on `main` get. CI uses its own token.

## A new headset joins

1. Its maintainers, or an owner who invites them, open an issue in
   [overpressure/overpressure](https://github.com/overpressure/overpressure/issues): the headset, its SoC, the
   people, where their work is today.
2. An owner creates `overpressure/<codename>`, the team `<codename>` and their rulesets (and a `soc-<soc>` team
   when the SoC is new) and the repository's social preview, then invites the people: last, since GitHub mails
   the invitation at once.
3. `core` adds the headset everywhere: its room's icon and its social card in brand, its room in matrix (which
   Goggles creates and sets up), its layer branch, its line in `.github/layers`, its rulesets and tag rule in
   linux, its folders and CODEOWNERS entries in packages, its row in the organization's profile
   ([profile/README.md](profile/README.md)); after its first release, its entry in overpressure's catalogue and CI.
4. The headset follows
   [docs/adding-a-headset.md](https://github.com/overpressure/overpressure/blob/main/docs/adding-a-headset.md),
   whose [organization's part](https://github.com/overpressure/overpressure/blob/main/docs/adding-a-headset.md#the-organizations-part)
   lists every step of 2 and 3 with its settings.
