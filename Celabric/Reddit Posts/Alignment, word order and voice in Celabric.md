I finally completed working on these and wanted to share with you. If you have some questions or find some inconsistencies, please tell me.
# Alignment

Celabric morphosyntactic alignment is nominative-accusative with secondary object construction. This means that subject is always in nominative, patient of monotransitive verbs are in accusative as is recipient of ditransitive verbs, and the theme of ditransitive verbs are on thematic case.

(1) Intransitive construction
```
xjyl trerfratr phalfna
NOM  horse     sleep[PRS.IND]
```
_"The horse sleeps"_

(2) Monotransitive construction
```
xjyl trerfratr cher         ja  tørm
NOM  horse     see[PRS.IND] ACC food
```
_"The horse sees the food"_

(3) Ditransitive construction
```
xjyl trerfratr fer           ja  drørphr jyn tørm
NOM  horse     give[PRS.IND] ACC cow     THM food
```
_"The horse gives the cow food"_

The objects are called primary (O1) (marked with accusative) and secondary (O2) (marked with thematic) not direct or indirect.
# Word order

Although the word order in Celabric is flexible and can be classified as free, there is some more common word order. The verb is most flexible and can be placed anywhere (sometimes even in between of a noun and it's attributive adjectives, but rarely).

Because Celabric tends to drop articles, the word order then becomes necessary to determine the subject and objects. If one or more arguments lack articles the nominative-accusative-thematic order (Subject - primary object - secondary object) is implied. But if the arguments have articles, they can be placed in any position.

For example, all these orders are valid:

(4) S-V-O1-O2
```
xjyl trerfratr fer           ja  drørphr jyn tørm
NOM  horse     give[PRS.IND] ACC cow     THM food
```
_"The horse gives the cow food"_

(5) S-O2-O1-V
```
xjyl trerfratr jyn tørm ja  drørphr fer
NOM  horse     THM food ACC cow     give[PRS.IND]
```
_"The horse gives the cow food"_

(6) V-O1-S-O2
```
fer           ja  drørphr xjyl trerfratr jyn tørm
give[PRS.IND] ACC cow     NOM  horse     THM food
```
_"The horse gives the cow food"_

But when one or more articles are absent, it is the order that defines the arguments:

(7) Nominative article absent
```
trerfratr  fer           ja  drørphr jyn tørm
horse[NOM] give[PRS.IND] ACC cow     THM food
```
_"The horse gives the cow food"_

(8) Nominative and thematic articles absent
```
trerfratr  fer           ja  drørphr tørm
horse[NOM] give[PRS.IND] ACC cow     food[THM]
```
_"The horse gives the cow food"_

In the example 8 the thematic case is implied to **[[tørm]]** only because nominative and accusative were already used. If the order is rearranged, than the meaning is changed as well:

(9) Nominative and thematic articles absent
```
tørm      trerfratr  fer           ja  drørphr
food[NOM] horse[THM] give[PRS.IND] ACC cow
```
_"The food gives the cow horse"_
# Voice

When the verb requires x arguments and less then x arguments are present in the sentence, the voice becomes something other than active. There are 8 voices in total for ditransitive verbs, 4 voices for monotransitives, 2 voices for intransitives and 1 voice for impersonal verbs:

1. Intransitive:

| Voice              | Subject? |
| ------------------ | -------- |
| Acitve             | yes      |
| Impersonal passive | no       |

(10) Intransitive active
```
xjyl trerfratr phalfna
NOM  horse     sleep[PRS.IND]
```
_"The horse sleeps"_

(11) Intransitive impersonal passive
```
phalfna
sleep[PRS.IND]
```
_"(It) is being slept"_

2. Monotransitive

| Voice              | Subject? | Object? |
| ------------------ | -------- | ------- |
| Active             | yes      | yes     |
| Antipassive        | yes      | no      |
| Passive            | no       | yes     |
| Impersonal passive | no       | no      |

(12) Monotransitive active
```
xjyl trerfratr cher         ja  tørm
NOM  horse     see[PRS.IND] ACC food
```
_"The horse sees the food"_

(13) Monotransitive antipassive
```
xjyl trerfratr cher
NOM  horse     see[PRS.IND]
```
_"The horse sees"_

(14) Monotransitive passive
```
cher         ja  tørm
see[PRS.IND] ACC food
```
_"The food is seen"_

(15) Monotransitive impersonal passive
```
cher
see[PRS.IND]
```
_"(It) is seen"_

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

(16) Ditransitive active
```
xjyl trerfratr fer           ja  drørphr jyn tørm
NOM  horse     give[PRS.IND] ACC cow     THM food
```
_"The horse gives the cow food"_

(17) Ditransitive secondary antipassive
```
xjyl trerfratr fer           ja  drørphr
NOM  horse     give[PRS.IND] ACC cow
```
_"The horse gives the cow"_

(18) Ditransitive primary antipassive
```
xjyl trerfratr fer           jyn tørm
NOM  horse     give[PRS.IND] THM food
```
_"The horse gives food"_

(19) Ditransitive full antipassive
```
xjyl trerfratr fer
NOM  horse     give[PRS.IND]
```
_"The horse gives"_

(20) Ditransitive full passive
```
fer           ja  drørphr jyn tørm
give[PRS.IND] ACC cow     THM food
```
_"The cow is given food"_

(21) Ditransitive primary passive
```
fer           ja  drørphr
give[PRS.IND] ACC cow
```
_"The cow is given"_

(22) Ditransitive secondary passive
```
fer           jyn tørm
give[PRS.IND] THM food
```
_"The food is being given"_

(23) Ditransitive impersonal passive
```
fer
give[PRS.IND]
```
_"(It) is being given"_
