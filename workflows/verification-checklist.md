# Verification checklist for public portfolio docs

- [ ] Required files exist and indexes link to them.
- [ ] Markdown relative links resolve from the file that contains them.
- [ ] `git diff --check` passes.
- [ ] `git submodule status` shows only intended public submodules.
- [ ] GitHub links are checked with `gh repo view` or `gh pr view` where possible.
- [ ] Case studies include Summary, Problem, Solution, Verification, and Why this matters where applicable.
- [ ] Private-work material is sanitized and says so explicitly.
- [ ] Scan changed markdown for secrets, private IPs, private URLs, chat IDs, tokens, cookies, overclaiming, and attribution errors.
- [ ] False positives from safety-rule wording are documented separately.
- [ ] Final report lists completed tasks, manual tasks, risks, public links, and shareable founder text.
