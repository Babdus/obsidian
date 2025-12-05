I have combined two great ideas: [vicarious we](https://www.reddit.com/r/conlangs/comments/1h6c8pu/conlang_feature_idea_vicarious_we/) and [binary pronouns](https://www.reddit.com/r/conlangs/comments/1awbn3u/idea_for_8_pronouns_based_on_binary_counting/), expanding them into ternary system as suggested by some in the comments.

First I want to define some participants, every possible combination of which will give us distinct pronouns.
##### Participants

1. **S** - Speaker(s): 1st person, generally singular, but can be plural: multiple personalities or three-headed dragon
2. **W** - Speaker's group: A group of people or other beings that the speaker perceives as their peers in a given context. This group excludes actual speaker. Can be singular - one particular person from this group, or plural.
3. **L** - Listener(s): 2nd person, singular or plural
4. **Y** - Listener's group: A group of listener's peers excluding actual listener(s). Singular or plural.
5. **O** - Other(s): 3rd person, singular or plural
##### Slots

Because each of those 5 participants can either be absent (**0**), be singular (**1**) or be plural (**n**) the ternary system will work the best. In total there will be 3^5 = 243 distinct pronouns. We can easily assign the morphemes and fully grammaticalize this feature having 5 slots for each participant. Example morphemes can be:

| Participant | Singular | Plural |
| ----------- | -------- | ------ |
| **S**       | pa       | da     |
| **W**       | u        | ro     |
| **L**       | je       | vi     |
| **Y**       | i        | o      |
| **O**       | la       | ny     |
Only 0th pronoun (The one, where every participant is 0, e.g. "no one") will require different word (for example **kek**), because in systematic way the 0th pronoun would have been an empty word.
##### Ternary system

For the example situations assume that the speaker is from England and the listener is from Germany.

| **S** | **L** | **O** | **W** | **Y** | Romanization | IPA        | Meaning                                               | Example                                                                                 |
| ----- | ----- | ----- | ----- | ----- | ------------ | ---------- | ----------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 0     | 0     | 0     | 0     | 0     | kek          | /kɛk/      | No one                                                | No one has seen the sun here.                                                           |
| 1     | 0     | 0     | 0     | 0     | pa           | /pɑ/       | I                                                     | I love toast.                                                                           |
| n     | 0     | 0     | 0     | 0     | da           | /dɑ/       | I (with alter egos)                                   | We have a DID                                                                           |
| 0     | 1     | 0     | 0     | 0     | je           | /jɛ/       | you (singular)                                        | Do you live in Saarland?                                                                |
| 0     | n     | 0     | 0     | 0     | vi           | /vi/       | you (plural)                                          | When did you meet?                                                                      |
| 0     | 0     | 1     | 0     | 0     | la           | /lɑ/       | they (singular)                                       | They are a really nice person.                                                          |
| 0     | 0     | n     | 0     | 0     | ny           | /nɨ/       | they (plural)                                         | They're very nice people.                                                               |
| 0     | 0     | 0     | 1     | 0     | u            | /u/        | (vicarious) we (singular)                             | We invented the first computer (meaning another Englishman, Charles Babbage)            |
| 0     | 0     | 0     | n     | 0     | ro           | /ħo/       | (vicarious) we (plural)                               | We have been fighting each other for more than hundred years (not me, but my people)    |
| 0     | 0     | 0     | 0     | 1     | i            | /i/        | (vicarious) you (singular)                            | You invented the printing (another German, Johannes Gutenberg)                          |
| 0     | 0     | 0     | 0     | n     | o            | /o/        | (vicarious) you (plural)                              | You have been burning witches as well (not you per se, but other Germans).              |
| 1     | 1     | 0     | 0     | 0     | paje         | /pɑjɛ/     | (inclusive dual) we                                   | We don't get along, sorry.                                                              |
| n     | 1     | 0     | 0     | 0     | daje         | /dɑjɛ/     | (inclusive dual) we (with alter egos)                 | We are not making any progress (I, my alter egos, and and singular you)                 |
| 1     | n     | 0     | 0     | 0     | pavi         | /pɑvi/     | (inclusive plural) we                                 | Where are we going, guys? (I and you, plural listeners)                                 |
| n     | n     | 0     | 0     | 0     | davi         | /dɑvi/     | (inclusive plural) we (with alter egos)               | We are all fine (I, with DID and you, plural listeners)                                 |
| ...   | ...   | ...   | ...   | ...   | ...          | ...        | ...                                                   | ...                                                                                     |
| 1     | 0     | 0     | n     | 0     | paro         | /pɑħo/     | (exlusive) we                                         | We are eating beans every morning.                                                      |
| ...   | ...   | ...   | ...   | ...   | ...          | ...        | ...                                                   | ...                                                                                     |
| 1     | 0     | 1     | n     | n     | parojeo      | /pɑħojɛo/  | (inclusive) we                                        | We are Europeans.                                                                       |
| ...   | ...   | ...   | ...   | ...   | ...          | ...        | ...                                                   | ...                                                                                     |
| 1     | 1     | 1     | 1     | 1     | paujeila     | /pɑʊjɛɪlɐ/ | (all-inclusive) we (only singular from each category) | We all live in this WG (I, you (singular), my friend, your friend and one other person) |
Obviously I will not list all 243 possibilities but the pattern is clear I think.

Even more pronouns can be achieved by having not only 0, 1 and n members in each slot, but 2, 3.. or all (n is not necessarily all, it is plural but not all from that group).

