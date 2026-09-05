---
title: "The Point Is the Kid, Not the Model"
description: "Why I'm building AI for a five-year-old learning to say 'rabbit' instead of another demo."
pubDate: 2026-08-26
---

The most convincing AI demo I have seen in the last year was not a demo. It was a five-year-old
saying "rabbit" into an iPhone over and over, not because anyone was making them, but because the
game was fun and they wanted the next turn.

What struck me was what was missing. No adult sighing, no patient correction, nothing in the room
with an opinion about the attempts that came out wrong. It just listened again, and the kid kept
going, and ten minutes of practice happened where two would have. Nobody clapped and there was no
benchmark score, but a model had actually made a person's day easier, which is more than I can say
for most of what I have watched on a stage.


## The gap I keep noticing

There is an enormous amount of energy going into making models more capable, and comparatively
little going into pointing them at the boring, high-friction places where people are already
struggling. That asymmetry is where I want to spend my time.

Speech practice is a good example. The knowledge is not the bottleneck. Speech-language
pathologists know exactly what a child needs to work on. The bottleneck is that the child sees
them for thirty minutes a week, and the other six days and twenty-three and a half hours depend on
a tired parent at 7pm with a printed word list, no way to tell whether the /s/ that just came out
was close enough, and no idea what to try tomorrow.

That is not a knowledge problem. It is a "there aren't enough hours or experts to go around"
problem. It is precisely the kind of problem where a machine that can listen carefully, ten
thousand times, without getting bored, is worth something real.

## What "helping a real human" actually requires

Scoring a child's pronunciation sound by sound is a technical problem which is mostly solved.

The challenge lies on the domain side of the equation:
* How to make a user want to keep practicing their speech?
* How to make a user feel un-judged and criticized?
* How to combine speech analysis with gamified practice, without trying to write an entire speech language pathologist into a codebase?


 Deciding what to
do with that score is where all the difficulty lives, and almost none of it is machine learning:

- **A single bad recording must never label a child.** A dropped microphone, a sibling shouting,
  a kid who is just done for the day. You need a minimum number of attempts before any conclusion
  is allowed to count, which means building patience into the system on purpose.
- **A ranking is not a diagnosis.** Every child has a weakest sound, including a child who is
  doing completely fine. This is a practice app, not a diagnostic instrument, and it does not
  replace a speech-language pathologist. What it can honestly say is "these are the sounds we
  should spend tomorrow's five minutes on" - an ordering used to choose words, not a verdict on
  the child. The clinician decides what is a problem; we just make the days
  between appointments count. That is a product decision, not a model decision, and getting it
  wrong does real harm.
- **You have to keep asking questions you know the answer to might have changed.** If every
  practice card comes from the child's current problem list, you never find out that a sound got
  fixed. Some deliberate portion of the work has to be spent learning rather than drilling.
- **The child has to want to open it tomorrow.** No amount of correct sound selection matters if
  the thing is a chore. The best-targeted practice session in the world scores zero if it does not
  happen.

None of that shows up in an eval. All of it is the difference between a system that helps and a
system that merely works.

## Where the actual work goes

Every word Stella can practise needs an illustration a small child recognizes instantly and a
clean prompt recording. The selection logic can be perfect - it can know with certainty that this
child needs to practise /ʃ/ at the start of words - and it is worth nothing if we have no picture
for a single word that fits. Today the illustrated vocabulary is a fraction of the words we have
prepared.

So the gap is not between what the model can do and what the child needs. The gap is between what
the system knows to do and what the system has been given to do it with. That is where most of my
time goes, and I have come to think that is true of a lot of applied AI work: the intelligence
arrives first, and then you spend years building the boring scaffolding that lets it touch
anything.

That is fine. The scaffolding is the job. The model is not the point.

The kid is.
