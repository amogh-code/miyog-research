# ASK — overview

ASK is the language in which MIYOG's worlds are written. One program holds a world's dynamics, its hidden truth and its author's expectations. The engine sees none of the program text. It is offered actions and receives opaque observation marks that can only be compared for equality.

## Main constructs (ASK 0.2)

| Construct | Role |
|---|---|
| `world`, `algorithm`, `strategy` | program forms |
| `kind`, `state` | bounded value domains and variables |
| `action ... when ...` | guarded, parameterised interventions |
| `every n ticks: ...` | rules applied as time passes |
| `conserve`, `require` | quantities and invariants; violating one makes a step undefined |
| `hidden`, `observe` | what the engine may and may not see |
| `event`, `goal` | named conditions and quantities |
| `expect` | the author's beliefs, read only by an external checker |

Every step returns a state, *undefined*, or *exhausted* (out of fuel). Execution is bounded and deterministic.

## Example

`examples/fuse3.ask` (from the paper, Section 5.5):

```
world Fuse3
state taps : 0..5
state light : 0..1
hidden taps
action tap: taps = taps + 1 if taps < 4 else taps; light = 1 if taps + 1 >= 3 else 0
action rest: light = light
action reset: taps = 0; light = 0
```

The engine is offered `tap`, `rest`, `reset` and `wait`, and sees only a mark for `light`. The lamp lights on the third tap. A law such as "tapping changes nothing visible" holds for the first two taps and fails on the third.
