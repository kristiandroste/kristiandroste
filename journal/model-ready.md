---
title: "Model Ready"
installment: "Part 8"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["Mu 171K"]
---

# Model Ready

Part 8.

The student had been waiting on the training machine since August. As unit one came together, Kris Droste brought it into the launch: "**we can also consider including the tiny foundation model in this initial firmware release as something that devs can build on.**"

The AI recommended against putting it on the device at launch, for robustness, and suggested running it on the user's computer instead. Kris's answer, quoted at the start of this story, was that the model "**fits on a chip precisely for the reason of fitting it on a chip.**"

On September 19 the software around the device took the GNU Affero General Public License, a copyleft license that keeps derived work open, with commercial licenses available. The AI had suggested Apache, a license with fewer conditions. Kris: "**huh? i said copy left not apache.**"

The firmware's version of the model has to give the same answers as the training code. For the model the device runs today, Mu 171K, the check was run on a computer on October 4, with the learned numbers stored at 8 bits each exactly as the device holds them. The two agree to a cosine similarity of 1.000000000 over 16 test windows, a score on which 1 is a perfect match, and no number differs by more than 0.0000004.

On September 20, reviewing the firmware's design, the AI proposed taking the model out. Kris: "**you cannot just haphazard propose something like 'remove the ai foundation model'! what are you even thinking? you are drifting.**"

Then the pieces came together. Firmware 1.0.1, on September 24, proved that signed updates worked, and unit one passed its acceptance test five times out of five. Firmware 1.1.0, on September 25, moved the filters that clean the signal onto the device, and the device declares them in the data it sends. The heads, the small add-ons that turn the model's numbers into answers, would be open for anyone to train and load.

On September 25, for the first time, a unit carried the model and ran it, and the firmware reported the model ready.

The next morning, the model needed fourteen seconds per window.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- Kris's answer, quoted at the start of this story, was that the model "**fits on a chip precisely for the reason of fitting it on a chip.**" On September 19 the software around the device took the GNU Affero General Public License, a copyleft license that keeps derived work open, with commercial licenses available.
- For the model the device runs today, Mu 171K, the check was run on a computer on October 4, with the learned numbers stored at 8 bits each exactly as the device holds them.
- The two agree to a cosine similarity of 1.000000000 over 16 test windows, a score on which 1 is a perfect match, and no number differs by more than 0.0000004.
- On September 20, reviewing the firmware's design, the AI proposed taking the model out.
- Firmware 1.0.1, on September 24, proved that signed updates worked, and unit one passed its acceptance test five times out of five.
- Firmware 1.1.0, on September 25, moved the filters that clean the signal onto the device, and the device declares them in the data it sends.
- On September 25, for the first time, a unit carried the model and ran it, and the firmware reported the model ready.

## Sentences that quote the record, verbatim from the text above

- As unit one came together, Kris Droste brought it into the launch: "**we can also consider including the tiny foundation model in this initial firmware release as something that devs can build on.**" The AI recommended against putting it on the device at launch, for robustness, and suggested running it on the user's computer instead.
- Kris's answer, quoted at the start of this story, was that the model "**fits on a chip precisely for the reason of fitting it on a chip.**" On September 19 the software around the device took the GNU Affero General Public License, a copyleft license that keeps derived work open, with commercial licenses available.
- Kris: "**huh? i said copy left not apache.**" The firmware's version of the model has to give the same answers as the training code.
- Kris: "**you cannot just haphazard propose something like 'remove the ai foundation model'! what are you even thinking? you are drifting.**" Then the pieces came together.

## Terms, as defined in the series glossary

- **Window.** Four seconds of signal, the piece the models work on.
- **Firmware.** The software that runs inside a device.
- **Model.** A program that is trained on examples rather than written line by line.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Mu 17.8M, Mu 492K, Mu 171K.** The IntoMind Mu models: the teacher, the larger student, and the student that runs on the IntoMind One.
- **Acceptance test.** The full set of checks a unit has to pass.
