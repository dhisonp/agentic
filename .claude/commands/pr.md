Create or update a pull request.

Usage: /pr <action> [pr-number]

Actions:
- create: Create new PR for current branch
- update: Update existing PR (optionally specify PR number)

Examples:
/pr create
/pr update
/pr update 123

Instructions:
1. Parse action from $ARGUMENTS (create or update) and optional PR number
2. Launch general-purpose agent with model='haiku'
3. Instruct agent to:
   - create: Analyze git history, draft PR description following .github/pull_request_template.md, create PR using gh CLI
   - update: Fetch PR details, analyze changes, update PR description following .github/pull_request_template.md using gh CLI
4. Return PR URL to user

IMPORTANT: Follow .github/pull_request_template.md strictly with minimal, human-like descriptions. Then, assign author as myself.