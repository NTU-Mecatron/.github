# GitHub Development Workflow

## Overview
This guide outlines the standard workflow for contributing to this project, from task assignment through code review and merging.

## 1. Mark Task as In Progress

When you start working on a task:
- Update the task status on Notion to **"In Progress"** to communicate that you've begun development
- This helps the team track active work and avoid duplicate efforts

## 2. Create a Feature Branch

Navigate to the relevant git submodule and create a new branch following this naming convention:

```bash
cd auv_ws/src/related_package  # Navigate to the submodule
git checkout -b type/descriptive-name
```

**Branch naming format:** `type/descriptive-name`

- **type**: Category of change
  - `feat` — New feature
  - `fix` — Bug fix
  - `doc` — Documentation updates
  - `refactor` — Code restructuring
  - `test` — Tests or test updates
  - `chore` — Build, dependency, or configuration changes

- **descriptive-name**: Brief, lowercase description (use hyphens, not underscores)

**Examples:**
```bash
git checkout -b feat/autonomous-docking
git checkout -b fix/battery-calibration
git checkout -b doc/update-api-reference
```

## 3. Make Changes and Push

Develop your feature or fix on your branch:

```bash
# Make your changes
git add .
git commit -m "Brief, clear description of changes"
git push -u origin your-branch-name
```

**Commit message guidelines:**
- Keep messages concise but descriptive
- Use imperative mood: "Add feature" not "Added feature"
- Reference the Notion task or GitHub issue if applicable

## 4. Create a Pull Request

Open a PR within the submodule repository (not `auv_ws` itself):

**PR Title Format:**
```
type(scope): Brief description

Example: feat(vision): Add obstacle detection algorithm
```

**PR Description Template:**

Include the following in your PR description (Recommended Structure):

```markdown
## Task/Issue
Notion task: [Link to Notion](https://link-to-notion-task)
or
Fixes GitHub Issue: [#123](https://github.com/your-repo/issues/123)

## Changes
- Change 1
- Change 2
- Change 3

## Testing
- How you tested these changes
- Any edge cases considered

## Notes
- Any important implementation details
- Potential breaking changes
- Questions for reviewers
```

**Request reviewers and assign them to the PR.**

## 5. Update Task Status and Notify Reviewers

- Change the Notion task status to **"Under Review"**
- Tag the assigned reviewer(s) in Notion to notify them of the pending review

## 6. Address Feedback and Merge

During code review:
- Address any feedback from reviewers
- Push updated commits to your branch
- Merge your branch with main if needed to resolve conflicts
- Request re-review once changes are made

Once approved:
- Merge your branch into main
- Delete the feature branch after merging
- Update the Notion task status to **"Done"**

## Best Practices

- **Keep branches up-to-date:** Rebase with main every 2-3 days to prevent merge conflicts
  ```bash
  git fetch origin
  git rebase origin/main
  git push -f origin your-branch-name
  ```

- **Keep commits clean:** Use meaningful commit messages and group related changes together

- **Keep PRs focused:** Limit each PR to a single feature or fix for easier review

- **Keep PRs small:** Limit the number of files changed in the PR. Usually should be less than 10 files

- **Follow code standards:** Refer to [coding_guidelines.md](coding_guidelines.md) before submitting

- **Don't force push to main:** Only force push to your feature branch if absolutely necessary

## Quick PR checklist

* [ ] Matches repository formatting & style
* [ ] Clear PR description and testing steps
* [ ] Notifies affected owners/reviewers