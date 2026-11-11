# Claude PFD Generator

By Scott Duncan. Find me on [LinkedIn](https://www.linkedin.com/in/scottduncanai/) or at [scottduncanai.com](https://scottduncanai.com/).

**Describe a process in plain English. Get an editable process flow diagram.**

Claude PFD Generator is a [Claude skill](https://code.claude.com/docs/en/skills) that turns a process description into a conceptual PFD. It guides Claude through laying out the equipment, drawing process streams and control loops, and checking the result before delivery. No coding experience is required.

![Conceptual PFD of the C-201 depropanizer with an overhead condenser, reflux drum and pump, and kettle reboiler](skills/pfd-generator/examples/c-201-distillation-column.png)

*A depropanizer PFD generated with the skill, including process flows and control logic. [Open the editable SVG](skills/pfd-generator/examples/c-201-distillation-column.svg).*

## What you get

- An editable SVG with equipment, process streams, instrumentation, and control loops.
- The Python script that generated the drawing, so Claude can revise it when you request a change.
- Engineering assumptions and any limitations identified while drawing.

## Install

Choose the option that matches how you use Claude.

### Claude Code

1. Click **Code → Download ZIP** on this repository and extract the ZIP.
2. Open the extracted `skills` folder. Copy `pfd-generator` into `.claude/skills/` in your home folder. Create the folders if they do not exist. To install it for a single project, use that project's `.claude/skills/` folder instead.
3. Restart Claude Code and open the folder where you want to save your drawings.

Claude can help install the Python packages listed in `skills/pfd-generator/scripts/requirements.txt` when needed.

You can also install through Claude Code's plugin commands:

```text
/plugin marketplace add ScottDuncanAI/claude-manufacturing-skills
/plugin install pfd-generator@claude-pfd-generator
```

### Claude.ai

1. Download [pfd-generator.zip](https://github.com/ScottDuncanAI/claude-manufacturing-skills/releases/download/skills-latest/pfd-generator.zip). Leave it zipped.
2. In **Settings → Capabilities**, enable **Skills** and **Code execution and file creation**.
3. Go to **Customize → Skills**, select **+ → Create skill**, upload the ZIP, and enable it.

## Draw your first PFD

Once the skill is installed, type a process description into Claude:

> Draw a PFD of a steam-heated, agitated tank with temperature and level control.

Claude uses the skill when your request matches its description. It may ask questions about the process before drawing.

Open the SVG in your browser and review the equipment, streams, and controls. If a change is needed, describe it in the same conversation. The drawing's labels are editable text.

For a guided exercise, follow [Start here](https://scottduncanai.com/start-here#sd-pfd).

## How it works

The skill gives Claude a drawing workflow, engineering conventions, and reusable SVG components. Claude plans the layout, generates the drawing with Python, and checks it for problems such as overlapping labels, crossed process lines, incorrect elevations, and incomplete control loops.

The skill instructs Claude to render and inspect the drawing, make corrections, and repeat. If rendering is unavailable, Claude must say that the drawing has not been visually checked.

## Repository layout

```text
.claude-plugin/marketplace.json       Claude Code plugin listing
skills/pfd-generator/
  SKILL.md                           Drawing instructions
  references/                        Instrumentation and layout conventions
  scripts/                           SVG components and Python dependencies
  examples/                          Example PFD and editable SVG
```

## Limits

The output is a conceptual PFD. It is not an issued-for-design P&ID, does not size equipment or relief devices, and does not perform hazard analysis. A qualified engineer must review the drawing before relying on it.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) to report a drawing issue or improve the generator.

## License

[MIT](LICENSE). The license covers the skill text and code. It does not make generated drawings correct or replace engineering judgment.
