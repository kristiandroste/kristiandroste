---
title: "Back to Signal"
installment: "Part 10"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["Mu 171K"]
---

# Back to Signal

Part 10.

Mu 171K does more than sum up a window. Along the way it describes the window in pieces. Each electrode's four seconds are cut into slices of a fifth of a second, 100 samples each, and each slice becomes a token, a list of 76 numbers. The device can send those tokens out.

The documentation said that a reconstruction head, an open add-on, would turn a token back into the slice of signal it came from. When that was tested on the device's own tokens, it scored an R² of −0.12. R² measures how much of a signal's variation is recovered: 1 is all of it, 0 is no better than a flat line, and below 0 is worse than that. The head had been trained on the pieces hidden during the teacher's kind of training, not on the tokens the device actually sends. The claim in the documentation, which the AI had written, was false.

Kris Droste ruled that it would be fixed, and the brief for the next run records the ruling: "The open reconstruction head must do what the docs say it does: turn a token the device sends into the slice of signal it came from." His response to the findings was blunt: "**my intuition is that you might be being lazy or drifting and that the correct thing has not yet been built.**"

The rebuilt reconstruction head is a decoder, a map from the model's numbers back to the signal, and it is linear, the simplest kind. It was scored on recordings from studies it never trained on, leaving out the windows with extreme amplitudes, about 4 percent of them. On the rest it recovers an R² of 0.660, and 0.668 on the studies kept aside only for final testing. It does best on slow rhythms and worst on fast ones: 0.87 from 1 to 4 cycles per second, 0.73 in the alpha range from 8 to 13, and 0.12 from 30 to 45.

The windows left out matter. They carry 92 percent of the signal's power, and with them included, the pooled R² falls to 0.058. The typical window, extreme ones included, is still recovered at a median R² of 0.68.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- Mu 171K does more than sum up a window.
- Each electrode's four seconds are cut into slices of a fifth of a second, 100 samples each, and each slice becomes a token, a list of 76 numbers.
- When that was tested on the device's own tokens, it scored an R² of −0.12.
- R² measures how much of a signal's variation is recovered: 1 is all of it, 0 is no better than a flat line, and below 0 is worse than that.
- It was scored on recordings from studies it never trained on, leaving out the windows with extreme amplitudes, about 4 percent of them.
- On the rest it recovers an R² of 0.660, and 0.668 on the studies kept aside only for final testing.
- It does best on slow rhythms and worst on fast ones: 0.87 from 1 to 4 cycles per second, 0.73 in the alpha range from 8 to 13, and 0.12 from 30 to 45.
- They carry 92 percent of the signal's power, and with them included, the pooled R² falls to 0.058.
- The typical window, extreme ones included, is still recovered at a median R² of 0.68.

## Sentences that quote the record, verbatim from the text above

- Kris Droste ruled that it would be fixed, and the brief for the next run records the ruling: "The open reconstruction head must do what the docs say it does: turn a token the device sends into the slice of signal it came from." His response to the findings was blunt: "**my intuition is that you might be being lazy or drifting and that the correct thing has not yet been built.**" The rebuilt reconstruction head is a decoder, a map from the model's numbers back to the signal, and it is linear, the simplest kind.

## Terms, as defined in the series glossary

- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Window.** Four seconds of signal, the piece the models work on.
- **Model.** A program that is trained on examples rather than written line by line.
- **Teacher, student, distillation.** A small model, the student, is trained to reproduce what a large model, the teacher, says about the same data.
- **Mu 17.8M, Mu 492K, Mu 171K.** The IntoMind Mu models: the teacher, the larger student, and the student that runs on the IntoMind One.
- **Token.** The list of numbers a model produces to describe one short slice of the signal.
- **Decoder.** A map from a model's numbers back to the signal. The open reconstruction head is a decoder.
- **Head.** A small add-on that turns a model's numbers into an answer, such as an estimate of age.
- **R².** How much of a signal's variation is recovered. 1 is all of it, and 0 is no better than a flat line.
