# Alignment

Celabric morphosyntactic alignment is nominative-accusative with secondary object construction. This means that subject is always in nominative, patient of monotransitive verbs are in accusative as is recipient of ditransitive verbs, and the theme of ditransitive verbs are on thematic case.
```gloss
\lbl Intransitive construction
\num 1
\gla xjyl trerfratr phalfna
\glb NOM horse sleep^[PRS.IND^]
\ft The horse sleeps
```
```gloss
\lbl Monotransitive construction
\num 2
\gla xjyl trerfratr cher ja tørm
\glb NOM horse see^[PRS.IND^] ACC food
\ft The horse sees the food.
```
```gloss
\lbl Ditransitive construction
\num 3
\gla xjyl trerfratr fer ja drørphr jyn tørm
\glb NOM horse give^[PRS.IND^] ACC cow THM food
\ft The horse gives the cow food
```
The objects are called primary (O1) (marked with accusative) and secondary (O2) (marked with thematic) not direct or indirect.
# Word order

Although the word order in Celabric is flexible and can be classified as free, there is some more common word order. The verb is most flexible and can be placed anywhere (sometimes even in between of a noun and it's attributive adjectives, but rarely).

Because Celabric tends to drop articles, the word order then becomes necessary to determine the subject and objects. If one or more arguments lack articles the nominative-accusative-thematic order (Subject - primary object - secondary object) is implied. But if the arguments have articles, they can be placed in any position.

For example, all these orders are valid:
```gloss
\lbl S-V-O1-O2
\num 4
\gla xjyl trerfratr fer ja drørphr jyn tørm
\glb NOM horse give^[PRS.IND^] ACC cow THM food
\ft The horse gives the cow food
```
```gloss
\lbl S-O2-O1-V
\num 5
\gla xjyl trerfratr jyn tørm ja drørphr fer
\glb NOM horse THM food ACC cow give^[PRS.IND^]
\ft The horse gives the cow food
```
```gloss
\lbl V-O1-S-O2
\num 6
\gla fer ja drørphr xjyl trerfratr jyn tørm
\glb give^[PRS.IND^] ACC cow NOM horse THM food
\ft The horse gives the cow food
```
But when one or more articles are absent, it is the order that defines the arguments:
```gloss
\lbl Nominative article absent
\num 7
\gla trerfratr fer ja drørphr jyn tørm
\glb horse^[NOM^] give^[PRS.IND^] ACC cow THM food
\ft The horse gives the cow food
```
```gloss
\lbl Nominative and thematic articles absent
\num 8
\gla trerfratr fer ja drørphr tørm
\glb horse^[NOM^] give^[PRS.IND^] ACC cow food^[THM^]
\ft The horse gives the cow food
```
In the example 8 the thematic case is implied to **[[tørm]]** only because nominative and accusative were already used. If the order is rearranged, than the meaning is changed as well:
```gloss
\lbl Nominative and thematic articles absent 2
\num 9
\gla tørm trerfratr fer ja drørphr
\glb food^[NOM^] horse^[THM^] give^[PRS.IND^] ACC cow
\ft The food gives the cow horse
```
# Voice

When the verb requires x arguments and less then x arguments are present in the sentence, the voice becomes something other than active. There are 8 voices in total for ditransitive verbs, 4 voices for monotransitives, 2 voices for intransitives and 1 voice for impersonal verbs:

1. Intransitive:

| Voice              | Subject? |
| ------------------ | -------- |
| Acitve             | yes      |
| Impersonal passive | no       |
```gloss
\lbl Active
\num 10
\gla xjyl trerfratr phalfna
\glb NOM horse sleep^[PRS.IND^]
\ft The horse sleeps
```
```gloss
\lbl Impersonal passive
\num 11
\gla phalfna
\glb sleep^[PRS.IND^]
\ft (it) is being slept
```

2. Monotransitive

| Voice              | Subject? | Object? |
| ------------------ | -------- | ------- |
| Active             | yes      | yes     |
| Antipassive        | yes      | no      |
| Passive            | no       | yes     |
| Impersonal passive | no       | no      |
```gloss
\lbl Active
\num 12
\gla xjyl trerfratr cher ja tørm
\glb NOM horse see^[PRS.IND^] ACC food
\ft The horse sees the food
```
```gloss
\lbl Antipassive
\num 13
\gla xjyl trerfratr cher
\glb NOM horse see^[PRS.IND^]
\ft The horse sees
```
```gloss
\lbl Passive
\num 14
\gla cher ja tørm
\glb see^[PRS.IND^] ACC food
\ft The food is seen
```
```gloss
\lbl Impersonal passive
\num 15
\gla cher
\glb see^[PRS.IND^]
\ft (It) is seen
```

3. Ditransitive:

| Voice                 | Subject? | Primary object? | Secondary Object? |
| --------------------- | -------- | --------------- | ----------------- |
| Active                | yes      | yes             | yes               |
| Secondary antipassive | yes      | yes             | no                |
| Primary antipassive   | yes      | no              | yes               |
| Full antipassive      | yes      | no              | no                |
| Full passive          | no       | yes             | yes               |
| Primary passive       | no       | yes             | no                |
| Secondary passive     | no       | no              | yes               |
| Impersonal passive    | no       | no              | no                |
```gloss
\lbl Active
\num 16
\gla xjyl trerfratr fer ja drørphr jyn tørm
\glb NOM horse give^[PRS.IND^] ACC cow THM food
\ft The horse gives the cow food
```
```gloss
\lbl Secondary antipassive
\num 17
\gla xjyl trerfratr fer ja drørphr
\glb NOM horse give^[PRS.IND^] ACC cow
\ft The horse gives the cow
```
```gloss
\lbl Primary antipassive
\num 18
\gla xjyl trerfratr fer jyn tørm
\glb NOM horse give^[PRS.IND^] THM food
\ft The horse gives food
```
```gloss
\lbl Full antipassive
\num 19
\gla xjyl trerfratr fer
\glb NOM horse give^[PRS.IND^]
\ft The horse gives
```
```gloss
\lbl Full passive
\num 20
\gla fer ja drørphr jyn tørm
\glb give^[PRS.IND^] ACC cow THM food
\ft The cow is given food
```
```gloss
\lbl Primary passive
\num 21
\gla fer ja drørphr
\glb give^[PRS.IND^] ACC cow
\ft The cow is given
```
```gloss
\lbl Secondary passive
\num 22
\gla fer jyn tørm
\glb give^[PRS.IND^] THM food
\ft The food is being given
```
```gloss
\lbl Impersonal passive
\num 23
\gla fer
\glb give^[PRS.IND^]
\ft (It) is being given
```
