# Contributing to Claude PFD Generator

Contributions should improve the accuracy, readability, or usability of generated PFDs.

## Report a drawing issue

Include the process description, the generated SVG, and a short explanation of what is wrong. Use public or synthetic examples rather than confidential plant drawings.

For installation problems, include your operating system, the Claude application you use, and the error message.

## Improve the generator

1. Identify whether the change belongs in the drawing workflow, the reference material, or the SVG helper code under `skills/pfd-generator/`.
2. Make a focused change and explain the engineering reason for it.
3. Generate a drawing that exercises the change. Inspect the SVG and a rendered preview for equipment placement, process flow, labels, and complete control loops.
4. Include the example and your checks in the pull request.

Keep the output editable and retain the conceptual-drawing limitations. Do not present generated drawings as approved engineering documents.
