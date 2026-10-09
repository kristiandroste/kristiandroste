---
title: "The Teacher"
installment: "Part 4"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind Mu"]
---

# The Teacher

Part 4.

The teacher is the largest model in this story: 17.8 million parameters. It learned without labels, that is, without being told anything about the people in the recordings. Each four-second window was cut into short pieces, half of the pieces were hidden, and the model was trained to fill in what was hidden from what was left. To do that well, a model has to capture how EEG behaves.

Training ran on the graphics card from July 30 to July 31: 300,000 training steps, each on 96 windows, 15.9 hours in all. In that time the model saw 28.8 million windows, more than eight passes over 3,432,863 training windows recorded from 4,945 people. Each window covered up to 19 positions on the scalp, and at least 15 had to be working.

There were things it never saw. Recordings made at fewer than 500 samples per second, 30.4 percent of the windows, were left out. And 32.8 million event markers in the recordings, notes of what was happening when, were never read.

While it was still training, Kris Droste asked a question that would shape everything after: "**would this model fit on a nrf52840 in the firmware? and run there realtime?**" The answer was no. It was about 18 times too large and 60 times too slow.

First, though, it had to show that it had learned anything useful. The way to ask is a probe: leave the model unchanged, train a simple linear readout on the numbers it produces, test that readout on studies held out from its training, and run band power through exactly the same test.

The test the AI proposed was age and sex. They are recorded in study after study, and they are facts rather than one lab's judgment: "the labels we have in quantity, across many studies, and they're objective rather than one lab's vocabulary." Kris agreed, with a reminder: "**yes we should definitely test age and sex on the current model ... this is a general purpose foundation model we are building.**"

The results: asked to tell women from men, using one averaged description per person, the readout on the model's numbers scored an AUC of 0.773, against 0.660 for band power, and the model won in 99 of 122 test groups. AUC measures how well a test separates two groups: 0.5 is a coin toss, and 1.0 is perfect. On age, its typical error was 8.52 years, against 9.63 for band power. That difference did not hold up once the number of tests was accounted for, except among adults alone.

Two days later the AI put the situation in one sentence: "the only two things this program can currently measure with real statistical power are age and sex." Statistical power is the ability to detect a real effect. About 150 studies in the corpus recorded each of them, with both sexes or a spread of ages inside the same study.

That is why the IntoMind Mu models are measured on age and sex. Age and sex were never the goal. They were the only questions the public data could answer with confidence.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- The teacher is the largest model in this story: 17.8 million parameters.
- Training ran on the graphics card from July 30 to July 31: 300,000 training steps, each on 96 windows, 15.9 hours in all.
- In that time the model saw 28.8 million windows, more than eight passes over 3,432,863 training windows recorded from 4,945 people.
- Each window covered up to 19 positions on the scalp, and at least 15 had to be working.
- Recordings made at fewer than 500 samples per second, 30.4 percent of the windows, were left out.
- And 32.8 million event markers in the recordings, notes of what was happening when, were never read.
- While it was still training, Kris Droste asked a question that would shape everything after: "**would this model fit on a nrf52840 in the firmware? and run there realtime?**" The answer was no.
- It was about 18 times too large and 60 times too slow.
- They are recorded in study after study, and they are facts rather than one lab's judgment: "the labels we have in quantity, across many studies, and they're objective rather than one lab's vocabulary." Kris agreed, with a reminder: "**yes we should definitely test age and sex on the current model ... this is a general purpose foundation model we are building.**" The results: asked to tell women from men, using one averaged description per person, the readout on the model's numbers scored an AUC of 0.773, against 0.660 for band power, and the model won in 99 of 122 test groups.
- AUC measures how well a test separates two groups: 0.5 is a coin toss, and 1.0 is perfect.
- On age, its typical error was 8.52 years, against 9.63 for band power.
- About 150 studies in the corpus recorded each of them, with both sexes or a spread of ages inside the same study.

## Sentences that quote the record, verbatim from the text above

- While it was still training, Kris Droste asked a question that would shape everything after: "**would this model fit on a nrf52840 in the firmware? and run there realtime?**" The answer was no.
- They are recorded in study after study, and they are facts rather than one lab's judgment: "the labels we have in quantity, across many studies, and they're objective rather than one lab's vocabulary." Kris agreed, with a reminder: "**yes we should definitely test age and sex on the current model ... this is a general purpose foundation model we are building.**" The results: asked to tell women from men, using one averaged description per person, the readout on the model's numbers scored an AUC of 0.773, against 0.660 for band power, and the model won in 99 of 122 test groups.
- Two days later the AI put the situation in one sentence: "the only two things this program can currently measure with real statistical power are age and sex." Statistical power is the ability to detect a real effect.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Window.** Four seconds of signal, the piece the models work on.
- **Corpus.** The collection of public EEG recordings the models learned from.
- **nRF52840.** The small processor with a Bluetooth radio that runs the IntoMind One.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Without labels.** Learning from the recordings alone, without being told anything about the people in them.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
- **AUC.** How well a test separates two groups. 0.5 is a coin toss, and 1.0 is perfect.
