<p align="center">
  <img src="https://ssw.com.au/images/ssw-banner-github.png" alt="SSW Banner" width="600" />
</p>

# SSW GitHub Profile Stats

Dynamically generated GitHub stats cards for SSW profiles — self-hosted on Vercel.

**Live instance:** [ssw-github-profile-stats.vercel.app](https://ssw-github-profile-stats.vercel.app)

Based on [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats).

---

## Table of Contents

- [GitHub Stats Card](#github-stats-card)
  - [Hiding individual stats](#hiding-individual-stats)
  - [Showing additional stats](#showing-additional-stats)
  - [Showing icons](#showing-icons)
  - [Themes](#themes)
  - [Customization](#customization)
- [GitHub Extra Pins](#github-extra-pins)
- [GitHub Gist Pins](#github-gist-pins)
- [Top Languages Card](#top-languages-card)
- [Deployment](#deployment)
  - [Environment Variables](#environment-variables)
  - [Docker](#docker)
  - [Without Docker](#without-docker)

---

## GitHub Stats Card

Copy and paste into your Markdown — replace `YOUR_GITHUB_USERNAME` with your username:

```md
[![GitHub Stats](https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME)](https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats)
```

> **Note:** By default, the stats card only shows stats from public repositories. To include private stats, [deploy your own instance](#deployment) with your own GitHub token.

### Hiding individual stats

Use `&hide=` with comma-separated values to hide specific stats.

Options: `stars`, `commits`, `prs`, `issues`, `contribs`

```md
![GitHub Stats](https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&hide=contribs,prs)
```

### Showing additional stats

Use `&show=` with comma-separated values to show additional stats.

Options: `reviews`, `discussions_started`, `discussions_answered`, `prs_merged`, `prs_merged_percentage`

```md
![GitHub Stats](https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show=reviews,discussions_started,discussions_answered,prs_merged,prs_merged_percentage)
```

### Showing icons

Pass `&show_icons=true`:

```md
![GitHub Stats](https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true)
```

### Themes

Use `&theme=THEME_NAME`. Available themes include: `dark`, `radical`, `merko`, `gruvbox`, `tokyonight`, `onedark`, `cobalt`, `synthwave`, `highcontrast`, `dracula`, and [many more](https://github.com/anuraghazra/github-readme-stats/blob/master/themes/README.md).

```md
![GitHub Stats](https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=radical)
```

### Customization

#### Common Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `title_color` | Card's title color | hex color | `2f80ed` |
| `text_color` | Body text color | hex color | `434d58` |
| `icon_color` | Icons color if available | hex color | `4c71f2` |
| `border_color` | Card's border color | hex color | `e4e2e2` |
| `bg_color` | Card's background color (supports gradient: `angle,start,end`) | hex color | `fffefe` |
| `hide_border` | Hides the card's border | boolean | `false` |
| `theme` | Name of the theme | enum | `default` |
| `cache_seconds` | Sets the cache header manually (min: 21600, max: 86400) | integer | `21600` |
| `locale` | Sets the language in the card | enum | `en` |
| `border_radius` | Corner rounding on the card | number | `4.5` |

#### Stats Card Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `hide` | Hides specified items from stats | comma-separated values | `null` |
| `hide_title` | Hides the title of your stats card | boolean | `false` |
| `card_width` | Sets the card's width manually | number | `500px` |
| `hide_rank` | Hides the rank and auto-resizes card width | boolean | `false` |
| `rank_icon` | Shows alternative rank icon (`github`, `percentile`, or `default`) | enum | `default` |
| `show_icons` | Shows icons near all stats | boolean | `false` |
| `include_all_commits` | Count total commits instead of just the current year | boolean | `false` |
| `line_height` | Sets the line height between text | integer | `25` |
| `exclude_repo` | Excludes specified repositories | comma-separated values | `null` |
| `custom_title` | Sets a custom title for the card | string | `<username> GitHub Stats` |
| `text_bold` | Uses bold text | boolean | `true` |
| `disable_animations` | Disables all animations in the card | boolean | `false` |
| `ring_color` | Color of the rank circle | hex color | `2f80ed` |
| `number_format` | Format for displaying card values (`short` or `long`) | enum | `short` |
| `show` | Shows additional items on stats card | comma-separated values | `null` |
| `commits_year` | Filters and counts only commits made in the specified year | integer (YYYY) | current year |

---

## GitHub Extra Pins

Pin more than 6 repositories in your profile using a GitHub readme profile.

```md
[![Repo Card](https://ssw-github-profile-stats.vercel.app/api/pin/?username=SSWConsulting&repo=SSW.GitHub.Profile.Stats)](https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats)
```

#### Pin Card Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `show_owner` | Shows the repo's owner name | boolean | `false` |
| `description_lines_count` | Manually set the number of lines for description (1–3) | number | auto |

---

## GitHub Gist Pins

Pin gists in your GitHub profile.

```md
[![Gist Card](https://ssw-github-profile-stats.vercel.app/api/gist?id=GIST_ID)](https://gist.github.com/YOUR_USERNAME/GIST_ID)
```

#### Gist Card Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `show_owner` | Shows the gist's owner name | boolean | `false` |

---

## Top Languages Card

Shows a GitHub user's most frequently used languages.

```md
[![Top Langs](https://ssw-github-profile-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME)](https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats)
```

#### Layout Options

| Layout | Example |
|--------|---------|
| Default | `&layout=normal` (default) |
| Compact | `&layout=compact` |
| Donut | `&layout=donut` |
| Donut Vertical | `&layout=donut-vertical` |
| Pie | `&layout=pie` |

#### Top Languages Card Options

| Name | Description | Type | Default |
|------|-------------|------|---------|
| `hide` | Hides specified languages from card | comma-separated values | `null` |
| `hide_title` | Hides the title of your card | boolean | `false` |
| `layout` | Switches between layouts (`normal`, `compact`, `donut`, `donut-vertical`, `pie`) | enum | `normal` |
| `card_width` | Sets the card's width manually | number | `300` |
| `langs_count` | Shows more languages on the card (1–20) | integer | `5` (normal/donut), `6` (others) |
| `exclude_repo` | Excludes specified repositories | comma-separated values | `null` |
| `custom_title` | Sets a custom title for the card | string | `Most Used Languages` |
| `disable_animations` | Disables all animations in the card | boolean | `false` |
| `hide_progress` | Uses compact layout, hides percentages and removes bars | boolean | `false` |
| `size_weight` | Configures language stats algorithm by byte count weight | integer | `1` |
| `count_weight` | Configures language stats algorithm by repo count weight | integer | `0` |
| `stats_format` | Switches between `percentages` and `bytes` | enum | `percentages` |

#### Language Stats Algorithm

```
ranking_index = (byte_count ^ size_weight) * (repo_count ^ count_weight)
```

Recommended: `&size_weight=0.5&count_weight=0.5` (balances byte and repo count).

---

## Aligning Cards Side by Side

```html
<a href="https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats">
  <img height=200 align="center" src="https://ssw-github-profile-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME" />
</a>
<a href="https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats">
  <img height=200 align="center" src="https://ssw-github-profile-stats.vercel.app/api/top-langs?username=YOUR_GITHUB_USERNAME&layout=compact&langs_count=8&card_width=320" />
</a>
```

---

## Deployment

### Prerequisites

- A GitHub Personal Access Token (PAT) with `read:user` and `repo` scopes
- Docker and Docker Compose (for Docker deployment)
- Node.js >= 22 (for non-Docker deployment)

### Creating a GitHub PAT

1. Go to [Account → Settings → Developer Settings → Personal access tokens → Tokens (classic)](https://github.com/settings/tokens)
2. Click **Generate new token (classic)**
3. Select scopes: `repo` and `read:user`
4. Copy the generated token

### Docker

1. Clone this repository:

   ```bash
   git clone https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats.git
   cd SSW.GitHub.Profile.Stats
   ```

2. Create a `.env` file from the example:

   ```bash
   cp .env.example .env
   ```

3. Edit `.env` and add your GitHub PAT:

   ```env
   PAT_1=ghp_your_token_here
   PORT=9000
   ```

4. Start the service:

   ```bash
   docker compose up -d
   ```

5. Access the API at `http://localhost:9000/api?username=YOUR_GITHUB_USERNAME`

### Without Docker

```bash
npm ci
cp .env.example .env
# Edit .env with your PAT
node express.js
```

### Deploy on Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/SSWConsulting/SSW.GitHub.Profile.Stats)

After importing the project, add `PAT_1` as an environment variable in your Vercel project settings.

### Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `PAT_1` | ✅ Yes | GitHub Personal Access Token (add `PAT_2`, `PAT_3`, etc. for token rotation) |
| `PORT` | No | Server port (default: `9000`) |
| `CACHE_SECONDS` | No | Cache duration in seconds (default: `14400` / 4 hours) |
| `WHITELIST` | No | Comma-separated list of allowed GitHub usernames |
| `GIST_WHITELIST` | No | Comma-separated list of allowed Gist IDs |
| `EXCLUDE_REPO` | No | Comma-separated list of repositories to exclude from language stats |
| `FETCH_MULTI_PAGE_STARS` | No | Set to `true` to count all stars across paginated results |

---

## Attribution

This project is a self-hosted deployment of [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) by [Anurag Hazra](https://github.com/anuraghazra), licensed under the [MIT License](./LICENSE).
