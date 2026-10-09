---
title: "Fourteen Seconds"
installment: "Prologue"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One", "Mu 492K"]
---

# Fourteen Seconds

Prologue.

On the morning of September 26, 2026, unit one was streaming to a laptop with its model switched on.

Unit one was the first IntoMind One, a wearable EEG device, that Kris Droste had built for validation. EEG is the electrical activity of the brain, picked up by electrodes resting on the scalp. The voltages are tiny, measured in millionths of a volt. The IntoMind One has four electrodes and a reference. It has an ADS1299, a chip that measures the electrodes 250, 500 or 1,000 times a second and turns each measurement into a number. And it has an nRF52840, a small processor with a Bluetooth radio that runs the device.

The model ran on that processor. A model, in this sense, is a program that is not written line by line. It is trained, shown example after example until the numbers inside it, its parameters, capture the patterns in the examples. This one took four seconds of signal at a time, measured 500 times a second, and turned each window into 96 numbers that describe it. The device sent those numbers to the laptop alongside the signal itself.

It had 491,904 parameters. It was a student, distilled from a much larger teacher: a model of 17.8 million parameters that had learned from 3,814 hours of public EEG recorded by other labs. Distillation means training the small model to reproduce what the large one says about each window. Later the student would be named Mu 492K.

Eight days earlier, the AI working with Kris had recommended a safer launch: run the model on the user's computer and keep it out of the firmware, the software inside the device. Kris refused: "**the model is tiny and fits on a chip precisely for the reason of fitting it on a chip.**"

Now it was on the chip, and it was slow. A window fills in four seconds. To keep up, the model has to finish each window before the next one is ready. That morning it needed about 14 seconds. Even working without pause, the chip could describe only one window in four.

Kris was not asking the model to do everything. That same morning he wrote: "**it doesnt need to do everything for everyone at launch. it just needs to have well defined utility and limitations.**"

How a model like this came to be on a chip like that had begun months earlier, on two tracks that had not yet met: a prototype board that Kris assembled himself, and a collection of other people's EEG.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- On the morning of September 26, 2026, unit one was streaming to a laptop with its model switched on.
- It has an ADS1299, a chip that measures the electrodes 250, 500 or 1,000 times a second and turns each measurement into a number.
- And it has an nRF52840, a small processor with a Bluetooth radio that runs the device.
- This one took four seconds of signal at a time, measured 500 times a second, and turned each window into 96 numbers that describe it.
- It had 491,904 parameters.
- It was a student, distilled from a much larger teacher: a model of 17.8 million parameters that had learned from 3,814 hours of public EEG recorded by other labs.
- Later the student would be named Mu 492K.
- That morning it needed about 14 seconds.

## Sentences that quote the record, verbatim from the text above

- Kris refused: "**the model is tiny and fits on a chip precisely for the reason of fitting it on a chip.**" Now it was on the chip, and it was slow.
- That same morning he wrote: "**it doesnt need to do everything for everyone at launch. it just needs to have well defined utility and limitations.**" How a model like this came to be on a chip like that had begun months earlier, on two tracks that had not yet met: a prototype board that Kris assembled himself, and a collection of other people's EEG.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Window.** Four seconds of signal, the piece the models work on.
- **ADS1299.** The chip in the IntoMind One that measures the electrodes and turns each measurement into a number. It is an ADC, the kind of chip that turns an analog voltage into digital numbers.
- **nRF52840.** The small processor with a Bluetooth radio that runs the IntoMind One.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Mu 17.8M, Mu 492K, Mu 171K.** The IntoMind Mu models: the teacher, the larger student, and the student that runs on the IntoMind One.
