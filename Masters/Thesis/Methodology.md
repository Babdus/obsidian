# Methodology
## Variables
The main objective of this research in order to investigate the grammatical function of the preverbs in the verb paradigm is to examine these variables and their combinations:
1. Preverbs
2. Paradigm blueprints of verbs
3. Semantic classes of verbs
4. Verb form
### Preverbs
The function of the preverb can be dependent on the actual preverb that is used to construct the verb form in question. Throughout the paper I will examine both derivationally productive and non-productive preverbs, since they all can be used in the modern verb paradigm formation as inflectional morphemes.[^1]
#### Simple preverbs
##### Productive preverbs
***და, გა, შე, ა, ჩა, წა, მი, მო***
##### Non-productive preverbs
***გან, აღ, შთა, წარ, უკუ, წიაღ***
#### Complex preverbs
##### Productive preverbs
***გადა, გამო, გადმო, შემო, ამო, ჩამო წამო, მიმო***
##### Non-productive preverbs
***დამო, გარდა, განმო, გარდამო, აღმო, შთამო, წარმო, უკმო, წიაღმო***
### Paradigm blueprints of verbs
Different verbs can produce the same grammatical forms in different ways. When at least one verbal form is inflected differently for the two distinct verbs, I say that those verbs have different paradigm blueprints. Conversely, if all the forms of two verbs are produced via exactly the same manner - they have the same paradigm blueprint. In the verb paradigm I explicitly include only the inflections by screeve (including sub-screeves[^2]) person and number (subject and object).[^3]

The verbs having the same paradigm blueprints produce the forms systematically using exactly the same affixes or mutations. These paradigms I took from the research of D. Melikishvili "ქართული ზმნის უღლების სისტემა", where she describes each of these paradigms in detail. She also provides the list of 15 000 Georgian verbs categorized in those paradigms.[^4]

The total number of the paradigms, which any Georgian verb can have, according to Melikishvili is 66. Though, she combines slightly differing paradigms into the same ones, consequently, for purely technical reasons I had to split all those kind of merges and the total number of paradigm blueprints goes up to 78. We can list these paradigm blueprints using the example verbs:[^5]

***ჭამს, აწვენს, წუხს, ჩქმეტს, ყვირის, ბღავის, თრთის, ცეკვავს, ყვინთავს, ჩურჩულებს, იძინებს, ამთქნარებს, ჰკირკიტებს, პატრონობს, მოძრაობს, ლოცულობს, კეცავს, აჭერს, ცრის, ზრდის, აგზავნის, ხატავს, ინახავს, კრავს, აშენებს, ადებინებს, აქებს, აკლებს, ათბობს, ნანობს, სესხულობს, არტყამს, იწერება, ეწერება, იდრიკება, ედრიკება, ინძრევა, ენძრევა, ირყევა, ერყევა, ირევა, ერევა, ერქმევა, ემთხვევა, იჭრება, ეჭრება, იზრდება, ეზრდება***[^5]

These blueprints can differ from each other, for example, by having an 'ე' or 'ი' as an aorist marker; or whether they form 'ოდ'-suffix forms in II resultative and III subjunctive; or whether the root vowel is changing in different screeves.
### Semantic classes of verbs
Different verbs also can be grouped by their meanings. For example the verb can be expressing the action or state, thus they will be grouped into **dynamic** and **static** semantic classes. We can have more detailed categorization, for example, we can group verbs in **perception** or **motion** semantic classes.

The one important semantic categorization mechanism is aktionsart or lexical aspect. Lexical aspect is a characteristic of verb which expresses a relation between the verbal action and the flow of time. For example, the verbs ***სცივა*** and ***სცივდება*** have different lexical aspects: the first conveys the **continues state** and the second - **starting of this state**. Aktionsart is an important semantic feature for this research, because one of the differentiating grammatical category of the verbal paradigm elements is aspect, e.g. the relation of the action of the verbal form to the flow of time.

One more semantic class, which could have important relation to the function of the preverbs, is **reporting verbs**, such as: ***ფიქრობს, ამბობს, ჰგონია, ახსოვს, აგონდება, ასკვნის*** etc. This class of verbs is interesting because of their correlation to the evidential or reporting screeves, in case of which the preverb functions has to be determined.[^6]
### Verb form
The last variable, against which the preverb functions will be examined, is the verb form itself. Meaning, which screeve (or sub-screeve[^2]), which subject person and number, and which object person and number does the form represents, and if it does have a preverb.
### Defining the variables
For each of the word-form in the corpus those 4 variables would be defined in this way:

***დავუჩქარო***
- preverb: **და**
- blueprint: **ამთქნარებს (უ prefix)**
- class: **inchoative**
- form:
	- screeve: **II subjunctive**
	- subject:
		- person: **1**
		- number: **singular**
	- object: *N/A*
## Verb form generation
### Methodology
In order to have all the possible forms of the verbs, I write a program using Python programming language. This program 
## Notes
[^1]: Saying that all these preverbs *can* be used doesn't necessarily imply that there are known instances in modern speech where at least one of those preverbs are present.  However, because there are indeed some usages of some non-productive preverbs, such as ***აღ***, or ***გან*** (***აღწერს***, ***განდევნის***), without further examination we can not rule out any of those non-productive ones, thus leaving them as variables to be considered in the data collection and analysis is preferable to omitting them without consideration. In the next chapters there will be shown that the hypothetical verb forms that will be constructed in the process will not compromise the overall analysis if those forms will not be found in the corpus. Consequently, if any of those derivationally non-productive preverbs appear to be completely absent from the modern verb paradigm construction, they also will not take part in the statistical analysis and just be omitted afterwards.
[^2]: Traditional screeves, as formulated by A. Shanidze will sometimes include several morphologically distinct verbal forms in the same screeve (e.g. ***წეროს*** and ***დაწეროს***). Thus, I introduced the notion of **sub-screeve** that will differentiate these kinds of distinct forms inside the screeves.
[^3]: Other kinds of formations like voice changing (***წერს*** -> ***იწერება***), valence changing (***იწერება*** -> ***ეწერება***), causatives (***წევს*** -> ***აწვენს***), or inchoatives (***მიყვარს*** -> ***მიყვარდება***) are not included in the same paradigm and those forms are analyzed as distinct lexemes, therefore they have their own paradigms. Their distinction is produced by derivational change, not inflectional.
[^4]: In the same book Melikishvili categorizes those paradigms into super-categories - "diatheses", but I don't go that deep into this categorization, since I only need the different kinds of paradigms independently from her interpretation.
[^5]: This number is not final and may be extended during the research if some of the Melikishvili's paradigms combine more than one strictly defined blueprints.
[^6]: These semantic classes are not yet completely defined, however, during the research I plan to outline much more strict groups using a measurable criteria.