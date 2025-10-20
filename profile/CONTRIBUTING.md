# Contributing

## Quick Start
- Please read our [short and sweet coding guidelines](./docs/coding_guidelines.md).
- Use our [recommended development workflow](./docs/dev_workflow.md) to make changes and test it.
- Use [first contributions](https://github.com/firstcontributions/first-contributions) to make contributions just like other GitHub projects.

## IMPORTANT NOTES

### 1. Always Use Pull Requests for Main Branch Changes

Never push changes directly to the main branch, regardless of your role. Follow this workflow:

1. Create a feature branch and develop your changes
2. Push your branch and open a pull request to main
3. Request review from the code owner or designated reviewers
4. Before merging, pull the latest main branch into your feature branch and resolve any conflicts
5. Merge your feature branch into main once all reviewers approve

This applies to everyone, including code owners.

### 2. Make Changes in Git Submodules, Not the Workspace Root

> Notes:
> We use `auv_ws` repository as an example in this contribution guide. The same rules should be applied to other packages in Mecatron Organiation.

Your changes must be committed to the appropriate submodules inside `auv_ws/src`, not directly to the `auv_ws` repository. (Except for adding new submodules, or change docs. Those should be advised by code owner and be careful to make changes on `auv_ws`)

**Incorrect approach:**
```bash
cd auv_ws/
git checkout -b new-feature  # ❌ Wrong location
```

**Correct approach:**
```bash
cd auv_ws/src/related_package  # e.g., BehaviorTree, vision_msgs, etc.
git checkout -b new-feature    # ✓ Correct location

# Make your changes, then:
git commit -am "Add feature description"
git push -u origin new-feature
```

Each submodule has its own git history and should be managed independently.

## Checklist
- Use same style and formatting as rest of code even if it's not your preferred one.
- Change any documentation that goes with code changes.
- Do not include OS specific header files or new 3rd party dependencies.
- Keep your pull request small, ideally under 10 files.
- Make sure you don't include large binary files.
- When adding new includes, make dependency is absolutely necessary.
- Rebase your branch frequently with main (once every 2-3 days is ideal).
- Make sure your code would compile on Windows, Linux and OSX.