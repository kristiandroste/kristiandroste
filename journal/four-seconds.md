---
title: "Four Seconds"
installment: "Part 9"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One", "Mu 171K"]
---

# Four Seconds

Part 9.

By the morning of September 26, the model on unit one was taking about 14 seconds to work through four seconds of signal. Kris Droste wanted the IntoMind One to run in real time, every window finished before the next arrived, and it was more than three times too slow.

He asked the training machine for two things: first the heads for age and sex, and then "**a distillation ladder to see how small the foundation model can go while still beating or matching psd**". PSD, the power spectral density, is the measurement band power is computed from. A ladder trains a series of ever smaller students the same way and stops at the first one that fails.

Two lines of work ran through the day. On the device, the firmware got faster: 14.13 seconds per pass, one run of the model over one window, then 9.97, then 8.63 by midday. It was still too slow.

On the training machine, an AI agent built the heads and climbed down the ladder at the same time, in a run of five hours and twenty-four minutes. A student of 240,480 parameters passed. One of 123,072 fell short, narrowly, at telling women from men. One of 170,772, trained in between, passed. That made 170,772 the smallest rung that still matched band power. It needed 14.6 million multiply-adds per window, the basic arithmetic steps of a model, against 43.5 million for the model on the device.

That night Kris ruled that it would ship. Nineteen minutes later it went onto unit one over Bluetooth, and after a restart early the next morning, each pass took 3.15 seconds. The device described a window every 4.2 seconds and lost no samples.

It was not free. Tests that followed showed that on every test of its heads, the smaller model did a little worse than the larger one.

On the firmware that units ship with, 1.4.5, the windows run back to back, and a pass takes 3.504 to 3.507 seconds, measured over 12 passes. It fits inside four.

The model was later named Mu 171K.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- By the morning of September 26, the model on unit one was taking about 14 seconds to work through four seconds of signal.
- On the device, the firmware got faster: 14.13 seconds per pass, one run of the model over one window, then 9.97, then 8.63 by midday.
- A student of 240,480 parameters passed.
- One of 123,072 fell short, narrowly, at telling women from men.
- One of 170,772, trained in between, passed.
- That made 170,772 the smallest rung that still matched band power.
- It needed 14.6 million multiply-adds per window, the basic arithmetic steps of a model, against 43.5 million for the model on the device.
- Nineteen minutes later it went onto unit one over Bluetooth, and after a restart early the next morning, each pass took 3.15 seconds.
- The device described a window every 4.2 seconds and lost no samples.
- On the firmware that units ship with, 1.4.5, the windows run back to back, and a pass takes 3.504 to 3.507 seconds, measured over 12 passes.
- The model was later named Mu 171K.

## Sentences that quote the record, verbatim from the text above

- He asked the training machine for two things: first the heads for age and sex, and then "**a distillation ladder to see how small the foundation model can go while still beating or matching psd**".

## Terms, as defined in the series glossary

- **Window.** Four seconds of signal, the piece the models work on.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Mu 17.8M, Mu 492K, Mu 171K.** The IntoMind Mu models: the teacher, the larger student, and the student that runs on the IntoMind One.
- **Pass.** One run of a model over one window.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
- **PSD.** The power spectral density, the measurement band power is computed from.
- **Real time.** Finishing each window of EEG before the next one is ready.
