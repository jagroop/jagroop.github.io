New Project Work Flow
=====================

## Notes

- Always keep your feature or bug branch synced with remote dev branch.
- Whenever you start working on a new feature or bug. Please create a separate branch for your work DO NOT work on dev or master branch
  i.e. ```git checkout -b feature-name```
- Push only when the work is done , DO NOT PUSH frequently.
- Please write decent commit messages.
- Once the work is done push your feature branch on remote repo
- Create a merge request.
- Source branch will be feature branch (The one you were working on) and
- Target branch will be dev branch
- After creating merge request make sure there are no conflicts.
- If all is good share merge request link with your Team Leader.

## Installation

1. Clone repository ( Don't forget to replace ```app-name``` with Application Name without spaces )

```bash
git clone <link-to-repo>.git app-name

cd app-name

git checkout dev

git checkout -b <feature-branch>
```

2. Install dependecies

Read Further installation instructions from project Readme file
