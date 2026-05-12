# OPC Skills

OPC Skills is a skill pack for building and operating a one-person company workflow.

The pack contains 9 AgentSkills-compatible skill folders under `skills/`:

- `opc-orchestrator`
- `opc-resource-audit`
- `opc-niche-positioning`
- `opc-value-proposition`
- `opc-business-model-design`
- `opc-mvp-designer`
- `opc-conversion-loop`
- `opc-asset-ops`
- `opc-dashboard-review`

Each skill folder contains a required `SKILL.md` file and optional supporting files.

## Install In Codex

Copy this prompt into Codex:

```text
Install all skills from https://github.com/zhuzhenbo127/opc/tree/master/skills:

- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-orchestrator
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-resource-audit
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-niche-positioning
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-value-proposition
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-business-model-design
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-mvp-designer
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-conversion-loop
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-asset-ops
- https://github.com/zhuzhenbo127/opc/tree/master/skills/opc-dashboard-review
```

If installing manually with Codex's skill installer, install the paths:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo zhuzhenbo127/opc \
  --ref master \
  --path \
  skills/opc-orchestrator \
  skills/opc-resource-audit \
  skills/opc-niche-positioning \
  skills/opc-value-proposition \
  skills/opc-business-model-design \
  skills/opc-mvp-designer \
  skills/opc-conversion-loop \
  skills/opc-asset-ops \
  skills/opc-dashboard-review \
  --method git
```

Restart Codex after installation.

## Install In OpenClaw

OpenClaw loads skills from workspace `skills/`, project `.agents/skills/`, personal `~/.agents/skills/`, and shared `~/.openclaw/skills`.

To install this pack into the current OpenClaw workspace:

```bash
git clone https://github.com/zhuzhenbo127/opc.git /tmp/opc-skills
mkdir -p ./skills
cp -R /tmp/opc-skills/skills/* ./skills/
```

Then start a new OpenClaw session or restart the gateway.

## Publish To ClawHub

To make the skills installable through:

```bash
openclaw skills install <skill-slug>
```

publish each skill folder to ClawHub:

```bash
npm i -g clawhub
clawhub login

clawhub skill publish ./skills/opc-orchestrator --slug opc-orchestrator --name "OPC Orchestrator" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-resource-audit --slug opc-resource-audit --name "OPC Resource Audit" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-niche-positioning --slug opc-niche-positioning --name "OPC Niche Positioning" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-value-proposition --slug opc-value-proposition --name "OPC Value Proposition" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-business-model-design --slug opc-business-model-design --name "OPC Business Model Design" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-mvp-designer --slug opc-mvp-designer --name "OPC MVP Designer" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-conversion-loop --slug opc-conversion-loop --name "OPC Conversion Loop" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-asset-ops --slug opc-asset-ops --name "OPC Asset Ops" --version 1.0.0 --tags latest,opc,one-person-company
clawhub skill publish ./skills/opc-dashboard-review --slug opc-dashboard-review --name "OPC Dashboard Review" --version 1.0.0 --tags latest,opc,one-person-company
```

After publishing, users can install individual skills from OpenClaw with:

```bash
openclaw skills install opc-orchestrator
```

## Recommended Start

After installing the pack, start with:

```text
opc-orchestrator
```

The orchestrator will guide the user through the workflow and decide which stage skill should be used next.
