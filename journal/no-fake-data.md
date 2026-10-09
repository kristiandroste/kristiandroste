---
title: "No Fake Data"
installment: "Part 3"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: []
---

# No Fake Data

Part 3.

On July 18, Kris Droste had a new piece of hardware, a graphics card, and he wanted "**to put it to some good use on this corpus.**" A graphics card, or GPU, is the kind of chip AI models are trained on. This one had 8 gigabytes of memory and sat in an external enclosure, connected by a cable to a small desktop computer with 16 gigabytes of memory. It became the training machine.

The AI working with Kris named the problem it could address. Every analysis so far had run on band power, which "discards phase, cross-channel structure, temporal dynamics, and waveform shape": it keeps how strong each rhythm is and throws away its timing, its shape and how the electrodes move together. A model that learned from the signal itself might see what band power could not. The plan put the corpus right first. Then the GPU work would begin with a test that could not fail quietly, "Brain age first", meaning a check of whether a model could tell a person's age from their EEG. Kris approved the plan: "**this looks good. approved.**" His priority was the data itself: "**what matters is that my data is clean and accurate.**"

What followed was a rebuild of the corpus on rules Kris set one by one.

On artifacts, the parts of a recording that are not brain activity: "**we are removing *mechanical* artifacts, such as electrode disconnections, during which the signal is *absent* by definition, but we are retaining *physiological* 'artifacts' because that is real signal, real eeg.**" A blink is physiological. An electrode coming loose is mechanical.

On purpose: "**i am much more interested in building real time systems with eeg than i am in building post hoc data analysis pipelines.**" Whatever was done to the corpus had to be something a device could do to a live signal.

On sample rates, where upsampling means inventing samples between real ones: "**upsampling is something i will not accept… it truly is foundation building that we are doing.**" For one evening the corpus was set to 250 samples per second. The decision was reversed the same evening, and 500 stood, the highest rate that every dataset in the corpus then reached without inventing samples.

On missing data, where interpolation means filling in a missing electrode by guessing from its neighbors: "**interpolation is and has always been a hard no. absolutely no fake data may enter the corpus.**"

And on who it was all for: "**the models are for the real intomind bci devices.**"

Kris to the AI, on removing duplicate recordings: "**excluded means purge, but nothing unique and fitting our criteria should be excluded… you are an ai engineer and a surgeon with a scalpel, not a lumberjack with a chainsaw**". Seven whole datasets and 458 recordings turned out to be byte-for-byte duplicates and were removed. People who appeared in more than one dataset were matched by each lab's own records, never by guessing from the signal.

On July 27 the rebuilt corpus was finished: 7,116,460 windows of four seconds from about 260 datasets, close to 400 gigabytes, with every value in microvolts.

Next came how to split the data between training and testing for the models to come. Kris proposed keeping each person's recordings together, then added: "**dont agree to something just because i suggested it.**" A measurement decided on a stricter rule: every recording from a study stays on one side of the split. Every model in this story was trained and tested that way.

On July 30 the teacher began to train.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- On July 18, Kris Droste had a new piece of hardware, a graphics card, and he wanted "**to put it to some good use on this corpus.**" A graphics card, or GPU, is the kind of chip AI models are trained on.
- This one had 8 gigabytes of memory and sat in an external enclosure, connected by a cable to a small desktop computer with 16 gigabytes of memory.
- On sample rates, where upsampling means inventing samples between real ones: "**upsampling is something i will not accept… it truly is foundation building that we are doing.**" For one evening the corpus was set to 250 samples per second.
- The decision was reversed the same evening, and 500 stood, the highest rate that every dataset in the corpus then reached without inventing samples.
- Seven whole datasets and 458 recordings turned out to be byte-for-byte duplicates and were removed.
- On July 27 the rebuilt corpus was finished: 7,116,460 windows of four seconds from about 260 datasets, close to 400 gigabytes, with every value in microvolts.
- On July 30 the teacher began to train.

## Sentences that quote the record, verbatim from the text above

- On July 18, Kris Droste had a new piece of hardware, a graphics card, and he wanted "**to put it to some good use on this corpus.**" A graphics card, or GPU, is the kind of chip AI models are trained on.
- Every analysis so far had run on band power, which "discards phase, cross-channel structure, temporal dynamics, and waveform shape": it keeps how strong each rhythm is and throws away its timing, its shape and how the electrodes move together.
- Then the GPU work would begin with a test that could not fail quietly, "Brain age first", meaning a check of whether a model could tell a person's age from their EEG.
- Kris approved the plan: "**this looks good. approved.**" His priority was the data itself: "**what matters is that my data is clean and accurate.**" What followed was a rebuild of the corpus on rules Kris set one by one.
- On artifacts, the parts of a recording that are not brain activity: "**we are removing *mechanical* artifacts, such as electrode disconnections, during which the signal is *absent* by definition, but we are retaining *physiological* 'artifacts' because that is real signal, real eeg.**" A blink is physiological.
- On purpose: "**i am much more interested in building real time systems with eeg than i am in building post hoc data analysis pipelines.**" Whatever was done to the corpus had to be something a device could do to a live signal.
- On sample rates, where upsampling means inventing samples between real ones: "**upsampling is something i will not accept… it truly is foundation building that we are doing.**" For one evening the corpus was set to 250 samples per second.
- On missing data, where interpolation means filling in a missing electrode by guessing from its neighbors: "**interpolation is and has always been a hard no. absolutely no fake data may enter the corpus.**" And on who it was all for: "**the models are for the real intomind bci devices.**" Kris to the AI, on removing duplicate recordings: "**excluded means purge, but nothing unique and fitting our criteria should be excluded… you are an ai engineer and a surgeon with a scalpel, not a lumberjack with a chainsaw**".
- Kris proposed keeping each person's recordings together, then added: "**dont agree to something just because i suggested it.**" A measurement decided on a stricter rule: every recording from a study stays on one side of the split.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Corpus.** The collection of public EEG recordings the models learned from.
- **Model.** A program that is trained on examples rather than written line by line.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
- **Real time.** Finishing each window of EEG before the next one is ready.
- **BCI.** A brain-computer interface.
