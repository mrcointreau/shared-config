---
layout: two-cols-header
---

# Git Config for Merging

::left::

### Purpose

Set commit identity for back-merge commits.

### Key idea

GitHub App = authentication, Git = identity.

### Steps

1. Set `user.name` and `user.email`
2. Use the bot's `noreply` email

::right::

```yaml
# From release.yml back-merge step
- name: Configure git identity
  run: |
    git config user.name "your-app[bot]"
    git config user.email "<BOT_ID>+your-app[bot]@users.noreply.github.com"
    # BOT_ID = your GitHub App's numeric ID (from App settings or API)
```

<div>

### Finding your app email

1. Go to any commit made by your app
2. Click the bot username → copy the noreply email
3. Or: `https://api.github.com/users/your-app[bot]` → `id` field

</div>

<div>

**Failure mode:** `Author identity unknown`

</div>

<!--
Here's a common gotcha: GitHub App token is for authentication, but git commits need a separate identity with user.name and user.email. If you see "Author identity unknown" errors, this is the fix. Use the bot's noreply email from the App settings page. Find your App's numeric ID in App settings or via the API; the email format is {ID}+your-app[bot]@users.noreply.github.com.
-->
