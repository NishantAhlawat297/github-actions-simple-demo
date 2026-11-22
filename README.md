# Simple GitHub Actions CI/CD demo

1. Push this project to a new GitHub repository on the `main` branch.
2. GitHub Actions runs `deploy.yml` on the initial push (simulated deployment).
3. Create a `feature/change-message` branch and edit `app.py` (for example, change the example numbers only).
4. Push your feature branch and open a pull request into `main`.
5. Open the PR's **Checks** tab to see the `CI - PR Checks` run.
6. After CI passes, merge the PR. The push to `main` triggers `CD - Deployment`.
7. Open **Actions** and check the log for `Deployment Successful!`.

To try a failing CI run, change `return a + b` in `app.py` to `return a - b`, push to the feature branch, and watch the test fail. Fix it and push again.

**Notes:** CD here only prints a message; it does not deploy anything. The CD workflow triggers on *any* push to `main`, not just PR merges. You can enforce successful tests before merging using GitHub branch protection or a ruleset requiring the `test` check.
