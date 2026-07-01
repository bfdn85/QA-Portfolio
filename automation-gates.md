# Automation Gates in CI/CD Pipeline

## Overview

One of the questions I get asked a lot in interviews is how I approach gating a pipeline with automation. This document walks through how I think about it and what I have seen work in practice.

---

## The Core Idea

A gate is simply a check that has to pass before the pipeline moves forward. If your tests fail, the pull request cannot be merged. If the merge cannot happen, the deployment cannot happen. That is what makes it a gate and not just a report.

The difference between running tests and gating on tests is huge. Tests that do not block anything get ignored over time. Gates enforce quality whether or not anyone is paying attention that day.

---

## How I Think About Gate Ordering

Not all tests should run at the same time or carry the same weight. I think about it in layers:

The first checks should be the fastest ones. Linting, formatting, simple unit tests. These catch obvious issues in seconds and give developers immediate feedback without making them wait for a full test run.

Integration tests come next. These take longer but catch issues that unit tests miss, especially around how different parts of the system talk to each other.

End-to-end tests like Playwright runs come last because they are the slowest. By the time we get here, the code has already passed the cheaper checks. If the E2E tests fail at this point, it is usually a real user-facing issue.

Only after everything passes does the deployment proceed.

---

## Branch Protection

In GitHub you can set branch protection rules so that no one can merge into main or staging without a green pipeline. That includes senior engineers. It takes the quality decision out of individual judgment and puts it into the process itself, which is where it belongs on a team that is moving fast.

---

## Handling Credentials Securely

Tests running in a pipeline need environment URLs, usernames, and passwords. These should never be hardcoded anywhere in the repo. In GitHub Actions we store them as encrypted secrets and reference them in the workflow. This is something I paid close attention to when contributing to pipeline work because exposed credentials in a CI config is a real security risk.

---

## Test Reports

One thing I always push for is making sure test reports are stored as artifacts after every run, even when the tests pass. When something fails in the pipeline it does not always look the same as when it fails locally. Having the full Playwright HTML report available after a CI run saves a lot of back and forth trying to reproduce what happened.

---

## My Experience With This

I contributed to a GitHub Actions pipeline where Playwright tests were set up as a required gate before deployments. My focus was on making sure the right tests were stable enough to block the pipeline, that credentials were handled properly through GitHub Secrets, and that the team always had visibility into test results through uploaded artifacts after every run.

---

## Why I Care About This

Any team can write tests. Not every team makes those tests matter. Gating the pipeline is what closes that gap. It means quality is not something that gets checked at the end, it is something that is enforced throughout.

---

*Part of my [QA Portfolio](https://github.com/bfdn85/QA-Portfolio)*
