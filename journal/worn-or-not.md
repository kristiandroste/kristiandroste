---
title: "Worn or Not"
installment: "Part 11"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One"]
---

# Worn or Not

Part 11.

On September 25, Kris Droste made generation a launch requirement: "**generation cannot wait. generation must ship with the product launch.**" Generation means producing a synthetic EEG signal, one that no brain made.

A day later he asked for it on the device itself: "**is there a way to make it so that the reconstruction head can run on the device, enabling a synthetic-stream mode. that would be ideal.**" The AI proposed driving the reconstruction head from a prior in token space, a model of which tokens are likely. Kris checked that he had it right: "**a prior in token space seems like what we have been converging on. it will allow the device to produce synthetic signal endlessly and reliably regardless of whether it is worn or not, right?**" He saw the point of it, "**a clean, reliable synthetic signal generator could be a real useful tool**", and set a condition: "**we should still measure it, since this is somethng that will need to go in the dev docs**".

The first attempt was told apart from real EEG by the encoder itself, the model that turns EEG into tokens, with an AUC of 0.999: almost perfect detection.

The brief for the next run set Kris's standard: the synthetic signal "must produce a signal that the encoder itself cannot tell from real EEG, or come as close as a device-sized generator can".

The generator that shipped is a small model, trained with the encoder in the loop. A linear judge, the same kind of simple readout used everywhere else in this story, scores it at an AUC of 0.552. Kris wanted the measurement reported either way: "**the measurement is a finding.**"

Firmware written on September 27 moved the generator onto the device, and it first ran on unit one early on September 28. With its ADC switched off, the IntoMind One can produce a synthetic signal for as long as it runs, worn or not. Every export of synthetic data is labeled as synthetic, with names such as "ch1_synthetic_uv".

The same day Kris set a rule: "**i think only one ai model should run at a time.**" While the generator runs, the encoder does not. Firmware 1.3.3, on September 28, made it so.

A last rule went back to July's design review and the battery rule that came out of it. On October 2 Kris wrote: "**no functions that requires the user to wear the device runs while plugged in. the generator for purely synthetic signal should still run.**" Firmware 1.4.0, the same day, refuses to stream real EEG on USB power. The synthetic signal still streams.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- On September 25, Kris Droste made generation a launch requirement: "**generation cannot wait. generation must ship with the product launch.**" Generation means producing a synthetic EEG signal, one that no brain made.
- The first attempt was told apart from real EEG by the encoder itself, the model that turns EEG into tokens, with an AUC of 0.999: almost perfect detection.
- A linear judge, the same kind of simple readout used everywhere else in this story, scores it at an AUC of 0.552.
- Kris wanted the measurement reported either way: "**the measurement is a finding.**" Firmware written on September 27 moved the generator onto the device, and it first ran on unit one early on September 28.
- Every export of synthetic data is labeled as synthetic, with names such as "ch1_synthetic_uv".
- Firmware 1.3.3, on September 28, made it so.
- On October 2 Kris wrote: "**no functions that requires the user to wear the device runs while plugged in. the generator for purely synthetic signal should still run.**" Firmware 1.4.0, the same day, refuses to stream real EEG on USB power.

## Sentences that quote the record, verbatim from the text above

- On September 25, Kris Droste made generation a launch requirement: "**generation cannot wait. generation must ship with the product launch.**" Generation means producing a synthetic EEG signal, one that no brain made.
- A day later he asked for it on the device itself: "**is there a way to make it so that the reconstruction head can run on the device, enabling a synthetic-stream mode. that would be ideal.**" The AI proposed driving the reconstruction head from a prior in token space, a model of which tokens are likely.
- Kris checked that he had it right: "**a prior in token space seems like what we have been converging on. it will allow the device to produce synthetic signal endlessly and reliably regardless of whether it is worn or not, right?**" He saw the point of it, "**a clean, reliable synthetic signal generator could be a real useful tool**", and set a condition: "**we should still measure it, since this is somethng that will need to go in the dev docs**".
- The brief for the next run set Kris's standard: the synthetic signal "must produce a signal that the encoder itself cannot tell from real EEG, or come as close as a device-sized generator can".
- Kris wanted the measurement reported either way: "**the measurement is a finding.**" Firmware written on September 27 moved the generator onto the device, and it first ran on unit one early on September 28.
- Every export of synthetic data is labeled as synthetic, with names such as "ch1_synthetic_uv".
- The same day Kris set a rule: "**i think only one ai model should run at a time.**" While the generator runs, the encoder does not.
- On October 2 Kris wrote: "**no functions that requires the user to wear the device runs while plugged in. the generator for purely synthetic signal should still run.**" Firmware 1.4.0, the same day, refuses to stream real EEG on USB power.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Encoder.** A model that turns EEG into numbers. The IntoMind Mu models are encoders.
- **Token.** The list of numbers a model produces to describe one short slice of the signal.
- **Head.** A small add-on that turns a model's numbers into an answer, such as an estimate of age.
- **AUC.** How well a test separates two groups. 0.5 is a coin toss, and 1.0 is perfect.
- **Synthetic signal.** EEG-like signal produced by a model rather than by a brain.
