# Project Rules

1. Always define the full user flow before generating UI: what happens after the user submits the form, not just the form itself.
2. Never accept AI-generated code without running it and testing the form manually (valid input, empty fields, wrong input).
3. Every prompt must include: file references, constraints, example behavior, and a verification step ("write it, then test it").
4. Every input must have a visible label and a clear validation error message.
5. A success message may only appear after a real save that passed validation.
6. Every button that moves the user to another step must go through the same validation as Save.
7. Validation errors must be visible to the user even when the field is inside a hidden tab or section.
