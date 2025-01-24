# Jinja Speech Helper Templates
Speech helper template macros for Home Assistant
## plural(word, qty, show_qty, suffix)
Pluralize a word when required.
- **word** - word to pluralize *[string]*
- **qty** - numerical quantity *[number]*
- **show_qty** - preceed the word with the quantity *[boolean]*
### Usage
    {% from 'speech_helpers.jinja' import plural %}
    You need to leave for work in {{ plural('minute', 10, true) }}!
#### Output
You need to leave for work in 10 minutes!
## plural_verb(qty)
Display proper verb for given quantity.
- **qty** - numerical quantity *[number]*
### Usage
    {% from 'speech_helpers.jinja' import plural_verb %}
    {% from 'speech_helpers.jinja' import plural %}
    {% set qty_apple = 5 %}
    {% set qty_orange = 1 %}
    There {{ plural_verb(qty_apple) }} {{ plural('apple', qty_apple, true) }}.
    The {{ plural('orange', qty_orange, false) }} {{ plural_verb(qty_orange) }} yummy.
#### Output
There are 5 apples.

The orange is yummy.
## array_to_clist(arr, title)
Convert an array of items to a comma separated list.
- **arr** - array of items *[list]*
- **title** - list items with title case *[boolean]*
### Usage
    {% from 'speech_helpers.jinja' import array_to_clist %}
    {% set active_types = ['garbage', 'recycle', 'yard waste'] %}
    Don't forget to take out the {{ array_to_clist(active_types, false) }} today!
#### Output
Don't forget to take out the garbage, recycle, and yard waste today!
## iarticle(word)
Add the apropriate indefinate article (a, an) before a word.  Numerical values will automatically be coverted to the text equivelent.
- **word** - word to preceed with an indefinate article *[string]*
### Usage
    {% from 'speech_helpers.jinja' import iarticle %}
    There is {{ iarticle(50) }} percent chance of rain today.
    There is {{ iarticle(85) }} kilometer difference in the commute.
    That was {{ iarticle('honourable') }} thing to do.
#### Output
There is a fifty percent chance of rain today.

There is an eighty five kilometer difference in the commute.

That was an honourable thing to do.
## number_words(number)
Convert a numerical value to it's text equivelent.
- **number** - a numberical value *[integer]*
### Usage
    {% from 'speech_helpers.jinja' import number_words %}
    {{ number_words(123456789) }}
#### Output
one hundred twenty three million four hundred fifty six thousand seven hundred eighty nine
## cardinal_direction(bearing)
Convert a numerical compass bearing to cardinal direction short form. (eg. NNW)
- **bearing** - a numberical bearing value (0-360) *[integer]*
### Usage
    {% from 'speech_helpers.jinja' import cardinal_direction %}
    {{ cardinal_direction(250) }}
#### Output
WSW
## full_cardinal_direction(bearing)
Convert a numerical compass bearing to cardinal direction long form. (eg. North-Northwest)
- **bearing** - a numberical bearing value (0-360) *[integer]*
### Usage
    {% from 'speech_helpers.jinja' import full_cardinal_direction %}
    {{ full_cardinal_direction(250) }}
#### Output
West-Southwest