# Workflow

## Overview
I built the same settings form twice. Round 1 (branch `[round1-branch]`)
used one vague prompt: "[paste your exact prompt]". Round 2 (branch
`[round2-branch]`) used a precise prompt with file references,
constraints (visible labels, inline errors), example behavior (empty name
shows "Name is required."), and a verification step ("write it, then test
it"), run through an explore-plan-code loop.

## What the diff shows
Round 1 (`Settings_form_fixed (1).html`, 330 lines) produced a four-tab
settings page (Profile, Notifications, Appearance, Privacy) saving to
localStorage. Round 2 (`settings-form.html`, 312 lines) produced a focused
form (name, email, password, notifications) with a separate `Validation`
module and a thank-you screen at `#thanks`.

## Correctness and edge cases
I tested the validators in Node. The email `a@b..c` passes in Round 1
(regex `^[^@\s]+@[^@\s]+\.[^@\s]+$`) and is rejected in Round 2. Empty and
whitespace-only names are rejected in both. A password of 8 spaces passes
in both. Round 1 validates only on Save click; Round 2 validates on blur
and keeps Save disabled until the form is valid.

## Accessibility
Round 2 ties each error to its input with `aria-describedby` and
`role="alert"`, and moves focus to the thank-you heading. Round 1 has
labels and `aria-invalid` but no `aria-describedby`, and its tabs lack
tabpanel roles. Round 1 also fails when a password error sits in the
hidden Privacy tab: `focus()` cannot reach it, so the user sees "Please
fix the highlighted fields" with nothing visible.

## Review effort
Round 1 took about [X] minutes, but I had to read 330 lines including
features I never asked for (avatar upload, delete account, language).
Round 2 took about [Y] minutes; the smaller scope and the isolated
validation module made it easier to test and review.

## AI mistakes I caught
In Round 2, the "Go to the next page" button skips validation and shows
"Your settings were saved successfully" even with empty fields. I caught
it by clicking the button on a blank form. [Describe your fix.] I also
found a dangling `aria-describedby="password-hint"` with no matching
element. In Round 1, the avatar message says to save to keep the photo,
but the photo is never saved.

## Rules learned
These findings led to rules 1 and 4 in CLAUDE.md: define the flow after
submit, and give every input a visible label and a clear error message.
