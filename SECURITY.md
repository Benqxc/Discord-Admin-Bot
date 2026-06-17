# Security Policy

## Reporting

Report vulnerabilities privately to [@Benqxc](https://github.com/Benqxc).

## Secrets Management

- Store `DISCORD_TOKEN` in `.env` only — never commit it
- `.env` is listed in `.gitignore`
- Rotate the token immediately at [Discord Developer Portal](https://discord.com/developers/applications) if leaked

## Bot Permissions

- Use least-privilege intents: only enable what the bot needs
- Review bot role hierarchy — bot role must be above roles it manages
- Audit slash command permissions per guild

## Configuration Files

JSON config files (`*.json`) store guild settings. They contain no secrets but may include channel/role IDs.

## Dependency Updates

```bash
pip install -U discord.py python-dotenv
```

## Known Risks

- Monolithic `bot.py` — large attack surface; review new commands carefully
- User-generated custom commands — sanitize output to prevent embed injection
