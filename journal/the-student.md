---
title: "The Student"
installment: "Part 6"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One"]
---

# The Student

Part 6.

The teacher was about 18 times too large for the chip in the IntoMind One and about 60 times too slow. Kris Droste asked what the alternative was: "**i mean training the tiny version on its own not as a student. what is the difference?**"

The answer became an experiment. On August 1 Kris set the goal: "**the goal is to build a foundation model that fits on the nrf along with the firmware weve built.**" And the comparison: "**we can compare training it 'from scratch' to training it by distilling the current model.**" The plan written that day describes the model as "A small EEG encoder that fits alongside existing nRF52840 firmware, as a tiny version of the same foundation model", not tied to one placement of the electrodes.

Kris added two demands: "**its supposed to be versatile,**" and "**the device can sit *anywhere* on the head.**" The plan records a third ruling, "EVERYTHING IN THE SIGNAL CHAIN IS CONFIGURABLE", and so the device was set to match the corpus: 500 samples per second and the same filter, which removes slow drift below half a cycle per second.

Could a model work anywhere on the head? The teacher was tested at 24 random placements, eight each with two, four and eight electrodes. With only two electrodes it told women from men with an AUC of 0.644, against 0.574 for band power. With four it scored 0.690 against 0.620, and with eight, 0.741 against 0.642. From one placement to another the scores moved by only 0.04 to 0.06. The plan recorded that this answered "the main risk in the whole approach".

Before any student was trained, the test it had to pass was written down: beat band power on sex and age.

Distillation works like this. The teacher looks at a window recorded at up to 19 positions and sums it up as 384 numbers. The student sees only the few electrodes a device has, two to eight of them, and is trained to produce the teacher's summary of the same window. It learns from information it will never have.

On August 1 six students were trained under the same rules, three from scratch and three by distillation, one of each for three ways of handling the electrode positions: always told where they were, never told, or told half of the time. The students trained from scratch did not beat band power. The distilled ones did. In all 12 comparisons between matching pairs, distillation came out ahead, in 11 of them by more than the margin of error. Telling the student where its electrodes were half of the time worked best. A student that was always told lost 1.24 years of accuracy on age when that information was taken away.

The model chosen had 491,904 parameters. The file the device later loaded for it, with its numbers stored at 8 bits each, is 503,072 bytes. It had been trained once, for 60,000 training steps.

The next day Kris set two directions: "**i want to train to largest model that will train and fit on this gpu, and i want to train tiny models successively down to the smallest model that beats bandpower.**" The large one was never trained. The small ones would be.

That evening Kris asked a plain question: "**wait so what does the little encoder actually do?**" The answer: "It turns 4 seconds of EEG into 96 numbers." It was, in the AI's words, "a feature extractor, not a detector." Those 96 numbers carried a little more than band power did about a person's age and sex. Whatever a user wants from them, a head, a small add-on trained on those numbers, turns them into an answer.

The student would not meet the device until September.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- The teacher was about 18 times too large for the chip in the IntoMind One and about 60 times too slow.
- On August 1 Kris set the goal: "**the goal is to build a foundation model that fits on the nrf along with the firmware weve built.**" And the comparison: "**we can compare training it 'from scratch' to training it by distilling the current model.**" The plan written that day describes the model as "A small EEG encoder that fits alongside existing nRF52840 firmware, as a tiny version of the same foundation model", not tied to one placement of the electrodes.
- Kris added two demands: "**its supposed to be versatile,**" and "**the device can sit *anywhere* on the head.**" The plan records a third ruling, "EVERYTHING IN THE SIGNAL CHAIN IS CONFIGURABLE", and so the device was set to match the corpus: 500 samples per second and the same filter, which removes slow drift below half a cycle per second.
- The teacher was tested at 24 random placements, eight each with two, four and eight electrodes.
- With only two electrodes it told women from men with an AUC of 0.644, against 0.574 for band power.
- With four it scored 0.690 against 0.620, and with eight, 0.741 against 0.642.
- From one placement to another the scores moved by only 0.04 to 0.06.
- The teacher looks at a window recorded at up to 19 positions and sums it up as 384 numbers.
- On August 1 six students were trained under the same rules, three from scratch and three by distillation, one of each for three ways of handling the electrode positions: always told where they were, never told, or told half of the time.
- In all 12 comparisons between matching pairs, distillation came out ahead, in 11 of them by more than the margin of error.
- A student that was always told lost 1.24 years of accuracy on age when that information was taken away.
- The model chosen had 491,904 parameters.
- The file the device later loaded for it, with its numbers stored at 8 bits each, is 503,072 bytes.
- It had been trained once, for 60,000 training steps.
- That evening Kris asked a plain question: "**wait so what does the little encoder actually do?**" The answer: "It turns 4 seconds of EEG into 96 numbers." It was, in the AI's words, "a feature extractor, not a detector." Those 96 numbers carried a little more than band power did about a person's age and sex.

## Sentences that quote the record, verbatim from the text above

- Kris Droste asked what the alternative was: "**i mean training the tiny version on its own not as a student. what is the difference?**" The answer became an experiment.
- On August 1 Kris set the goal: "**the goal is to build a foundation model that fits on the nrf along with the firmware weve built.**" And the comparison: "**we can compare training it 'from scratch' to training it by distilling the current model.**" The plan written that day describes the model as "A small EEG encoder that fits alongside existing nRF52840 firmware, as a tiny version of the same foundation model", not tied to one placement of the electrodes.
- Kris added two demands: "**its supposed to be versatile,**" and "**the device can sit *anywhere* on the head.**" The plan records a third ruling, "EVERYTHING IN THE SIGNAL CHAIN IS CONFIGURABLE", and so the device was set to match the corpus: 500 samples per second and the same filter, which removes slow drift below half a cycle per second.
- The plan recorded that this answered "the main risk in the whole approach".
- The next day Kris set two directions: "**i want to train to largest model that will train and fit on this gpu, and i want to train tiny models successively down to the smallest model that beats bandpower.**" The large one was never trained.
- That evening Kris asked a plain question: "**wait so what does the little encoder actually do?**" The answer: "It turns 4 seconds of EEG into 96 numbers." It was, in the AI's words, "a feature extractor, not a detector." Those 96 numbers carried a little more than band power did about a person's age and sex.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Window.** Four seconds of signal, the piece the models work on.
- **Corpus.** The collection of public EEG recordings the models learned from.
- **nRF52840.** The small processor with a Bluetooth radio that runs the IntoMind One.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Encoder.** A model that turns EEG into numbers. The IntoMind Mu models are encoders.
- **Head.** A small add-on that turns a model's numbers into an answer, such as an estimate of age.
- **Pass.** One run of a model over one window.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
- **AUC.** How well a test separates two groups. 0.5 is a coin toss, and 1.0 is perfect.
