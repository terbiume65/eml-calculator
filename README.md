# The two-button calculator

A calculator with only two keys: **1** and **eml(x, y) = eˣ − ln y**.

Every elementary function — addition, multiplication, roots, logarithms, trigonometry — can be built from that one binary operator plus the constant 1, so the whole scientific calculator reduces to a binary tree of identical nodes. This page lets you build such trees by hand and watch them evaluate.

Live: **https://terbiume65.github.io/eml-calculator/**

## What it does

- **1** fills the selected gap; **eml** splits a gap into two branches.
- Click any node to select it. Keyboard: `1`, `E`, `X`, `Y`, `Backspace`, `⌘Z`/`Ctrl+Z` to undo, `Esc` to reset.
- Live value, RPN string and token count (`K`) as you build.
- Trees fold automatically below depth 3, so large expressions stay readable.
- Eleven worked conversions, grouped as constants, one-variable and two-variable.

## Credit

The operator and its identities are from Andrzej Odrzywołek,
[All elementary functions from a single operator](https://arxiv.org/abs/2603.21852)
(arXiv:2603.21852, 2026). The two-button framing is from
[Numberphile's video on the paper](https://www.youtube.com/watch?v=LxVW3b8jVdE).

The chains here follow the paper's compiler constructions, not always the shortest known forms.

## Implementation

One self-contained `index.html`: plain HTML, CSS and vanilla JavaScript. No frameworks, no build step, no dependencies, no external requests. Complex arithmetic is implemented directly (`cexp`, `clog`, `cmul`, …) with explicit handling of the extended-real cases (`ln 0 = −∞`, `e^{−∞} = 0`) that the EML chains rely on.
