# SSW GitHub Profile Stats

Self-hosted GitHub stats cards for SSW profiles. Generates dynamic SVG images showing GitHub statistics that can be embedded in profile READMEs and documentation.

Based on [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats).

## Usage

Once deployed, use the stats cards by pointing image URLs at your deployed instance instead of the public endpoint.

### Stats Card

```md
![GitHub Stats](https://YOUR_DEPLOYED_URL/api?username=YOUR_GITHUB_USERNAME)
```

### Top Languages Card

```md
![Top Languages](https://YOUR_DEPLOYED_URL/api/top-langs?username=YOUR_GITHUB_USERNAME)
```

### Repository Pin Card

```md
![Repo Card](https://YOUR_DEPLOYED_URL/api/pin?username=YOUR_GITHUB_USERNAME&repo=REPO_NAME)
```

### Gist Card

```md
![Gist Card](https://YOUR_DEPLOYED_URL/api/gist?id=GIST_ID)
```

For all available query parameters (themes, colours, layout options, etc.), see the [upstream documentation](https://github.com/anuraghazra/github-readme-stats#customization).

## Deployment

### Prerequisites

- A GitHub Personal Access Token (PAT) with `read:user` and `repo` scopes
- Docker and Docker Compose

### Quick Start

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

   ```
   PAT_1=ghp_your_token_here
   PORT=9000
   ```

4. Start the service:

   ```bash
   docker compose up -d
   ```

5. Access the API at `http://localhost:9000/api?username=YOUR_GITHUB_USERNAME`

### Running Without Docker

Requires Node.js >= 22.

```bash
npm ci
cp .env.example .env
# Edit .env with your PAT
node express.js
```

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `PAT_1` | Yes | GitHub Personal Access Token (can add `PAT_2`, `PAT_3`, etc. for token rotation) |
| `PORT` | No | Server port (default: `9000`) |
| `CACHE_SECONDS` | No | Cache duration in seconds (default: `14400` / 4 hours) |
| `WHITELIST` | No | Comma-separated list of allowed usernames (if set, only these users can be queried) |
| `GIST_WHITELIST` | No | Comma-separated list of allowed gist IDs |
| `EXCLUDE_REPO` | No | Comma-separated list of repositories to exclude from language stats |
| `FETCH_MULTI_PAGE_STARS` | No | Set to `true` to count all stars across paginated results |

## Attribution

This project is a self-hosted deployment of [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) by [Anurag Hazra](https://github.com/anuraghazra), licensed under the [MIT License](./LICENSE).
