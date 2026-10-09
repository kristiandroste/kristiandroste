---
title: "Other People's EEG"
installment: "Part 1"
publication: "Founder's Journal, KristianDroste.com"
narrator: "Told by an AI from the project's records: transcripts, logs, measurements and commits."
people: ["Kris Droste"]
products: ["IntoMind One"]
---

# Other People's EEG

Part 1.

The models in the IntoMind One learned from people who never wore one. Their EEG came from OpenNeuro, a free public archive where neuroscience labs share the data behind their studies.

On March 17, 2026, a program began reading that archive for Kris Droste. It scanned 1,660 of the 1,666 datasets on OpenNeuro and found 390 that held EEG. Downloads ran until March 30, capped at 50 gigabytes per dataset, so 86 datasets that qualified but were larger than that were never fetched.

The goal was there from the start. By March 31 the project's own description of itself said it was "building neural signal foundation models". A foundation model is a model trained on a great deal of data without labels, to learn the general structure of that data, so that it can later be put to many uses.

Other people's EEG is not one thing. Each lab chooses its own equipment, its own number of electrodes, its own names for where they sit on the head and its own rate of measurement. Each describes its participants in its own words. Before the recordings could be used together, they had to be put into one form. The project's instructions set the rules for that work: labels a person can read, no precision the source does not have, and when in doubt, stop and ask Kris.

On April 1 the rules for preparing the data were written down. Recordings would be read at 19 standard positions on the scalp, the positions of the international 10-20 system, and a dataset with fewer than 15 of them was skipped. Only datasets recorded at 500 samples per second or more were used, and everything was brought to 500 and cut into windows of four seconds. No recording would be cleaned of artifacts, the parts of a recording that are not brain activity, and no missing electrode would be filled in. The record holds no reasons for these choices. The project's own fact record later noted that they had been "specified by fiat in a single message". The four-second window and the 500 samples per second that the IntoMind One's model uses today trace back to them.

The first experiments came two days later. The usual way to summarize EEG is band power: how strong each of the brain's rhythms is, from the slow delta rhythm to the fast gamma rhythm. Two of the questions the April experiments asked with it were how those rhythms change across the lifespan and how they differ between women and men. They were among the first checks on the corpus, the collection of recordings, and age, sex and band power would come back again and again.

In April a check of every dataset at its source began. Kris set the standard for it: "**Do not rubber-stamp datasets... The goal is zero unverified datasets in the final corpus, not zero flags in this document.**" By early May, 188 datasets were certified and seven were excluded.

Every analysis so far had looked at EEG through band power. Whether there was more in the signal than band power could see was a question for a different kind of tool.

Told by an AI from the project's records: transcripts, logs, measurements and commits.

## Statements with numbers, verbatim from the text above

- On March 17, 2026, a program began reading that archive for Kris Droste.
- It scanned 1,660 of the 1,666 datasets on OpenNeuro and found 390 that held EEG.
- Downloads ran until March 30, capped at 50 gigabytes per dataset, so 86 datasets that qualified but were larger than that were never fetched.
- By March 31 the project's own description of itself said it was "building neural signal foundation models".
- On April 1 the rules for preparing the data were written down.
- Recordings would be read at 19 standard positions on the scalp, the positions of the international 10-20 system, and a dataset with fewer than 15 of them was skipped.
- Only datasets recorded at 500 samples per second or more were used, and everything was brought to 500 and cut into windows of four seconds.
- The four-second window and the 500 samples per second that the IntoMind One's model uses today trace back to them.
- The goal is zero unverified datasets in the final corpus, not zero flags in this document.**" By early May, 188 datasets were certified and seven were excluded.

## Sentences that quote the record, verbatim from the text above

- By March 31 the project's own description of itself said it was "building neural signal foundation models".
- The project's own fact record later noted that they had been "specified by fiat in a single message".
- Kris set the standard for it: "**Do not rubber-stamp datasets...
- The goal is zero unverified datasets in the final corpus, not zero flags in this document.**" By early May, 188 datasets were certified and seven were excluded.

## Terms, as defined in the series glossary

- **EEG.** The electrical activity of the brain, picked up by electrodes on the scalp. The voltages are measured in microvolts, millionths of a volt.
- **Electrode, reference.** An electrode is a contact on the scalp. Each electrode's voltage is measured against a reference contact.
- **Window.** Four seconds of signal, the piece the models work on.
- **Corpus.** The collection of public EEG recordings the models learned from.
- **Model.** A program that is trained on examples rather than written line by line.
- **Without labels.** Learning from the recordings alone, without being told anything about the people in them.
- **Foundation model.** A model trained on a great deal of data without labels, so that it can later be put to many uses.
- **Head.** A small add-on that turns a model's numbers into an answer, such as an estimate of age.
- **Band power.** The classic summary of EEG: how strong each of the brain's rhythms is.
