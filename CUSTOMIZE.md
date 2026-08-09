# System manual: customize your profile

This profile uses a futuristic system-portal layout built from editable Markdown and original animated SVG files.

## File map

- `README.md` controls the layout, writing, links, technology icons, live statistics, and contact buttons.
- `assets/system/` contains all local neon panels and animations.
- `.github/workflows/arcade.yml` refreshes the Pac-Man contribution graph every day.

No JavaScript or build step is required. GitHub renders everything directly.

## Make a quick edit on GitHub

1. Open this repository on GitHub.
2. Select `README.md`.
3. Select the pencil icon labeled **Edit this file**.
4. Search for `EDIT ME` or the visible section title you want to change.
5. Use the **Preview** tab to review the result.
6. Select **Commit changes** when it looks right.

## Change the animated introduction

The typing animation is an image URL inside `README.md`. Its phrases appear after `lines=` and are separated by semicolons:

```text
lines=Software+Engineering+Intern;Full-Stack+%2B+Mobile+Developer
```

Use `+` for spaces. `%2B` displays a plus sign, and `%40` displays `@`.

## Edit the technical name header

Open `assets/system/technical-header.svg` and search for `KENYANG LUAL`. The same file contains the role line, education status, and system-status chips. Keep the name concise so it remains centered inside the interface frame.

## Change a portal destination

Each clickable portal follows this pattern:

```html
<a href="DESTINATION_URL">
  <img src="./assets/system/PORTAL.svg" alt="Description" />
</a>
```

Change only the `href` value to send visitors somewhere new. The three small portals currently lead to Guardian, AspireAI, and the complete project archive.

## Edit the neon SVG panels

Every file in `assets/system/` is plain SVG markup. The safest edits are text and colors:

- Visible wording is inside `<text>` elements.
- The main palette uses `#22D3EE` (cyan), `#8B5CF6` (violet), and `#EC4899` (pink).
- Backgrounds use `#020617` and `#071226`.
- Light text uses `#F8FAFC`; secondary text uses `#94A3B8`.
- Keep each file's existing `viewBox` value so it remains responsive.

Open an SVG in a browser to preview it. Animations use native SVG elements such as `<animate>` and `<animateTransform>`.

## Change the system-core statements

Open `assets/system/kenyang-core.svg` and search for these headings:

- `BUILD` describes your current engineering capabilities.
- `EXPLORE` describes subjects you are learning or experimenting with.
- `BELIEVE` describes the principles behind your work.

Keep each bullet concise so it remains inside its panel.

## Add or remove a technology

The technologies table in `README.md` uses icons from [Devicon](https://devicon.dev/). An icon cell looks like this:

```html
<td align="center">
  <img src="DEVICON_URL" width="34" alt="Technology" title="Technology" />
</td>
```

Replace an existing cell or add another table row with four cells to keep the grid balanced.

## Change the live statistics

The statistics and LeetCode cards are URL-based images in `README.md`. Change `username=Kenyang1` or `user=Kenyang1` only if your account name changes.

External stat-card services can occasionally be rate-limited. A temporary broken card usually resolves without any repository change.

## Start or repair the Pac-Man animation

The **Generate arcade contribution graph** workflow runs when it reaches `main` and then once every day.

If the animation has not appeared:

1. Open the repository's **Actions** tab.
2. Open **Generate arcade contribution graph**.
3. Select **Run workflow**.
4. Wait for the run to finish and confirm that an `output` branch was created.
5. Refresh your profile.

To remove the game, delete the `Pac-Man Contribution Grid` block from `README.md` and delete `.github/workflows/arcade.yml`.

## GitHub compatibility notes

- Profile README files cannot run JavaScript.
- GitHub removes most embedded CSS and `<style>` blocks from Markdown, but styles inside linked SVG files work.
- Relative images must be committed in the same branch as `README.md`.
- GitHub's **Preview** tab is the most accurate final check.
