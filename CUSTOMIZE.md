# Customize your game profile

Your profile is built from three files:

- `README.md` contains the words, links, badges, projects, and live stat cards.
- `assets/hero.svg` contains the cartoon banner.
- `.github/workflows/arcade.yml` refreshes the Pac-Man contribution animation once a day.

Everything uses plain text, so you can edit it directly on GitHub or in any code editor.

## Make a quick edit on GitHub

1. Open this repository on GitHub.
2. Select `README.md`.
3. Select the pencil icon labeled **Edit this file**.
4. Search for `EDIT ME` to jump to the parts designed for frequent changes.
5. Use the **Preview** tab to check the result.
6. Select **Commit changes** when it looks right.

## Change your character card

In `README.md`, find `PLAYER_01`. Edit the text in the **Current loadout** column. Keep the `|` characters because they define the table columns.

## Change your quests

Find `QUEST_LOG` in `README.md`. Each quest is a normal Markdown list item:

```md
- 🛡️ **Main quest:** Describe the goal here.
```

You can change the emoji, quest name, or description. Add another line beginning with `-` to add a quest.

## Feature a different project

Find `ADVENTURE_MAP` in `README.md`. A project row follows this pattern:

```md
| [**🎮 Project name**](https://github.com/Kenyang1/repository-name) | One-sentence mission. | `Tool` `Tool` `Tool` |
```

Replace the name, repository URL, mission, and power-ups. Keep one project per line.

## Add or remove a skill badge

Badges in `INVENTORY` come from [Shields.io](https://shields.io/). Duplicate an existing badge line, then change its label and logo. The profile palette is:

| Color | Hex | Used for |
| :--- | :--- | :--- |
| Midnight | `17213B` | Badge backgrounds |
| Gold | `FFCB6B` | Highlights |
| Mint | `6DE2BD` | Progress and success |
| Coral | `FF6B6B` | Calls to action |
| Blue | `6C9EFF` | Links and technology |
| Cream | `F7F3E8` | Light text |

## Edit the cartoon banner

Open `assets/hero.svg` as text. SVG is markup: shapes use tags such as `<rect>`, `<circle>`, `<path>`, and `<text>`.

The easiest safe changes are text and color:

- Change `KENYANG LUAL`, `FULL-STACK EXPLORER`, or the mission line inside `<text>` tags.
- Replace any palette hex code to recolor every matching element.
- Keep the `viewBox="0 0 1200 460"` value so the banner remains responsive.

After editing, open the SVG file in a browser to preview it.

## Start or repair the Pac-Man animation

The contribution game is created by the **Generate arcade contribution graph** workflow. It runs after the workflow is added to `main`, and then once every day.

If the animation has not appeared:

1. Open the repository's **Actions** tab.
2. Open **Generate arcade contribution graph**.
3. Select **Run workflow**.
4. Wait for the run to finish and confirm that an `output` branch was created.
5. Refresh your profile.

To remove the animation, delete the `ARCADE_MODE` block from `README.md` and delete `.github/workflows/arcade.yml`.

## Preview before publishing

GitHub's own **Preview** tab is the most accurate preview because GitHub limits some HTML and styling. Keep these compatibility rules in mind:

- GitHub README files do not run JavaScript.
- CSS files and `<style>` tags are not supported.
- Relative images such as `./assets/hero.svg` work after the files are committed together.
- Live stat cards need an internet connection and can occasionally be rate-limited by their providers.
