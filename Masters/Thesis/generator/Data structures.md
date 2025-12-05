##### parameters
```python
{
	"screeves": [
		("fut", "pres.direct.prfv")
		...
	],
	"prefixes": [
		"გვ:1_pl_obj.direct",
		...
	],
	"suffixes": [
		"ნ:3_pl_sbj.IIsubj.direct",
		...
	]
}
```
##### param_priority
```python
{
	"prefixes": {
		"ვ:1_sbj.direct": 0,
		"გვ:1_pl_obj.direct": 1,
		...
	},
	"suffixes": {
		...
		"ნ:3_pl_sbj.IIsubj.direct": 16,
		...
	}
}
```
##### category_to_parameter
```python
{
	"prefixes": {
		"direct": [
			{
				"param": "ვ:1_sbj.direct",
				"categories": {
					 "1_sbj",
					 "direct"
				}
			},
			{
				"param": "მ:1_sg_obj.direct",
				"categories": {
					"1_sg_obj",
					"direct"
				}
			}
			...
		]
		"1_sg_obj": [
			...
		]
		...
	},
	"suffixes": {
		...
	}
}
```
##### screeves
```python
[
	("pres", "pres.direct"),
	...
]
```
##### screeve_params
```python
{"pres", "direct"}
```
##### pers_params
```python
{"sg_obj", "2_obj", "2_sg_obj", "1_sbj", "sg_sbj", "1_sg_sbj"}
```
##### params
```python
{"pres", "direct", "sg_obj", "2_obj", "2_sg_obj", "1_sbj", "sg_sbj", "1_sg_sbj"}
```
##### rules
```python
{
	"prefixes": [
		(("ვ:1_sbj.direct", "გ:2_obj.direct"), 0),
		...
	],
	"suffixes": [
		(("ს:3_sg_sbj.direct", "ა:3_sg_sbj.impf.direct"), 0),
		...
	]
}
```
- The digit at the end of the rule indicates which of the params should be eliminated. 0: first, 1: second, 2: both.
##### affixes
```python
{
	"ვ:1_sbj.direct",
	"თ:pl_sbj.direct"
}
```