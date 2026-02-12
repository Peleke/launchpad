# Email 2: Quick Win

**Subject**: Try this with your next CI/CD debug -- takes 5 minutes
**Send**: Day 2
**Single job**: Give them a concrete win that validates the signup

---

Quick one.

Next time your pipeline breaks, before you push another commit, try this:

1. Install `act` (GitHub Actions local runner): `brew install act` or equivalent
2. Run your workflow locally: `act -j build`
3. Read the error message in your terminal -- not in the GitHub Actions UI

The error message locally is the same error you'd get after a 3-minute push-build-wait cycle. Except now you see it in 5 seconds. On your machine. Where you can actually debug it.

Module 4 of From 1 to Prod builds an entire CI/CD pipeline around this principle: validate locally, push confidently. No more "60 consecutive commits called 'fix pipeline error.'"

If you haven't started Module 1 yet -- no judgment. But when you're ready, `git checkout 01-linux` is waiting for you.

Reply and tell me: what's the dumbest pipeline error you've debugged? I have stories.

-- Peleke
