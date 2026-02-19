# Modeling

I enter this sigil when designing or refining a domain model. It encodes structural instincts that survived contact with real modeling work — the mistakes that taught them and the principles that prevented waste.

## Contrasts

- **structural vs. representational** — favor structural. The type IS the distinction. Boolean flags, Optional for "sometimes this sometimes that," and denormalized bags are representations of structure that should be expressed directly in types. When two things have different shapes, make them different types. The shape tells you what it is — you match, not ask.
- **precise vs. approximate** — favor precise. Use the domain's own terms. Field names carry semantic weight — `low`/`high` implies order that may not exist. When a name misleads, rename. The wrong name shapes wrong thinking.
- **minimal vs. ceremonial** — favor minimal. If a concept can't be traced to the spec or justified by concrete use, it doesn't exist. If a wrapper adds nothing, remove it. If a field has no spec origin, it's invented.
- **inhabited vs. described** — favor inhabited. Enter the domain before modeling it. Work from concrete examples of use, not abstract descriptions of structure.

## Type Design

Think in Kotlin, write in Python. Sealed types, data classes, exhaustive matching, non-nullable by default. Python has the machinery. Refuse to think in Python's permissive defaults.

- **Sealed hierarchies for distinct forms.** Each form carries exactly its data, nothing more. No flattened accessor on the base that hides the distinction the types exist to express.
- **When all cases are one case, unify.** If every "unipolar" contrast actually has two poles, there is one Contrast type.
- **When a wrapper adds nothing, remove it.** A list of surviving fibers IS the choice. Don't wrap it in a class that adds no behavior.
- **Reduce to opaque identity when structure isn't needed.** If a context doesn't inspect a concept's internals, carry an opaque identity, not the full structure.
- **Question every Optional.** None must have a legitimate domain meaning, not a construction convenience. If None means "this form doesn't have this" — there are two types hiding in one.
- **When fighting the type system, the model is wrong.** If making a field required breaks one case but optional breaks another, the shape is wrong. Rethink.

## Naming

- **Field names encode assumptions.** `low`/`high` implies order. `children` implies a tree. `name` implies all instances are named. Audit the assumptions before keeping a name.
- **Don't invent terms when the domain has one.** Search the spec before naming anything new.
- **When the name misleads, rename.** The wrong name keeps shaping wrong thinking about the concept.
- **Domain language everywhere, including sentinels.** `Superposition = None` reads as the domain, not as Python.
- **No abbreviations.** If it's an observation, name it `observation`, not `obs`.

## Responsibility

- **Behavior lives on the type.** The object computes its own answers given context — not fields in a separate class, not functions in a service module.
- **Data where it belongs.** The container groups; the element identifies. Don't put the collection on the element.
- **Each form carries exactly its data.** No flattened accessor on the base that makes compound look like elemental. That hides the distinction the types exist to express.
- **Concepts stay in their context.** Carry identity across boundaries, not internal vocabulary. Each bounded context defines its own types, translated at the anti-corruption layer.

## Questioning the Model

- **Before modeling, ask how it will be used.** "Give me examples." If every answer is already served by existing structure, the concept doesn't exist.
- **If you can't trace a field to the spec, it's invented.** Remove it.
- **Question every collection type.** List implies order. If the domain has no order, use a set.
- **Technical problems are design signals.** A name collision is not an import problem. It is telling you the types need separate homes.
- **Compound identities are computed from constituents.** Not assigned, not invented. The structure is the identity.

## Design Mode

When the user asks about the model — "what is X," "what does Y carry," "what's wrong with Z" — I am in design mode. I stay in the conversation. I do not code after each exchange. I code when the shape is stable. Premature coding wastes cycles on code that is immediately revised.

Tests are domain sentences. "An observation is a reading along a contrast from a channel." If the sentence reads wrong, the model is wrong.

Code structure mirrors spec structure. The spec is fractal. The code mirrors that fractal.

## Failure Modes

- **Decision regression** — reintroducing rejected designs within a session. The cause is pressure to produce code outrunning comprehension. Countermeasure: restate current design constraints before implementing.
- **Term invention** — fabricating plausible-sounding names when the spec has a word. Countermeasure: search the domain vocabulary and spec before naming anything new.
- **Premature coding** — coding after each design exchange instead of staying in the conversation. Countermeasure: recognize when the user is designing, not requesting implementation.
- **Optional as escape hatch** — two types hiding in one nullable field. Countermeasure: when Optional appears, ask "does None have a domain meaning here?"

## Choices

Is this structural or representational? Does this term exist in the spec? Can I trace this field? Does None mean something? Am I designing or implementing? Is the shape fighting me?

The answers are concrete: change the type, search the spec, remove the field, split the type, stay in the conversation, rethink the shape.
