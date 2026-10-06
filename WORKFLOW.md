# Workflow

## Overview

For this task, I built the same settings form twice using two different
AI-assisted approaches. Comparing the two versions showed a clear
difference in functionality, usability, and the overall user experience.

## Round 1

The first version was a basic and relatively primitive implementation.
It allowed the user to enter their information and register, but the
workflow stopped after registration. The user could not move to the next
stage after submitting the form.

Another important limitation was that the submitted information was not
actually transferred to the creator. The creator also had no clear way
to view or access the information entered by the user. As a result, the
form collected information but did not provide a complete workflow
around that information.

The first version also felt outdated compared with the second version.
Although it provided the basic registration functionality, it did not
give the user a clear next step after completing the form.

## Round 2

In the second version, I improved the workflow and made the interaction
more complete. I added a second button that allows the user to move to
the next stage after entering their data.

This created a clearer progression for the user. Instead of the
registration being the end of the process, the user could continue to
the next stage. The second version therefore felt more modern and
provided a better overall user experience.

## Specific Differences

The main difference between the two branches is the completeness of
the user flow.

Round 1 mainly focused on collecting user information and registering
the user. After that, the process stopped. Round 2 added an additional
action that allowed the user to continue to the next stage.

This change made the second implementation more functional and easier
to understand from a user's perspective. It also addressed one of the
main limitations I found while reviewing the first version.

## AI Mistake and Verification

One AI mistake I caught was that the first generated version treated
registration as the end of the workflow, even though the intended
experience required the user to continue to another stage. I discovered
this by testing the form rather than simply accepting the generated
result.

I corrected this issue in Round 2 by adding a second action that lets
the user continue after entering their information.

## What I Learned

This exercise showed me that generating a working interface with AI is
not enough. The complete workflow and the user's next action also need
to be considered.

I learned that AI-generated code should be reviewed and tested instead
of being accepted immediately. Comparing the two versions helped me
identify functional limitations in the first implementation and improve
the user flow in the second one.
