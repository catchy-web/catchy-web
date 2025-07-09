# catchy-lang - the catchy (programming) language

> Status: Idea and research step. See [this blog](../blog/maunzCache/human-centric-programming.md) for the inception.

## Wants and thoughts

- Signal words are easy to read and align better with natural language
- It starts of english based
- "Dialects" can be used to support catchy-lang to other world languages such as japanese, german, swedish, etc.
- To use it, the environment has to be as non-technical as possible e.g. be able to run it in a browser
- It is not hardware or perfomance optimized or optimizable but "application" oriented
- For inclusion, there is always feedback required: Visual, tactile, auditive, whatever is possible
- It will probably never compile itself, so it is okay to write it in an existing programming language
- It should be as simple as a prompt but not LLM based!
  > What is the sum of 3 and 5?
- Can it be "readable" by dyslexic people?
- Will we have words?
- The language should be an entry level for beginners, but usable for advanced
- It is ok to be verbose, if required

## Syntax ideas
```
write out:
with:
x as number 3
y as number 5
result of 3 + 5
```

### Experimental examples
```javascript
// Consider the script section of
// https://github.com/catchy-web/catchy-web/blob/main/games/1000-checkboxes.md?plain=1

function randomInteger(max) {
        return Math.floor(Math.random() * max);
    }

    const checkboxes = board.getElementsByTagName("input");

    function createChecker(range, min) {
        let time = randomInteger(range) + min;
        setInterval(() => {
            let randomBoxIndex = randomInteger(checkboxes.length);
            checkboxes[randomBoxIndex].checked = !checkboxes[randomBoxIndex].checked;
            time = randomInteger(range) + min;
        }, time * 100);
    }

    // set up board with around 50% of boxes checked
    for (const box of checkboxes) {
        if (Math.random() > 0.5) {
            box.checked = !box.checked;
        }
    }

    createChecker(10, 5);
    createChecker(20, 10);
    createChecker(40, 25);
    createChecker(80, 40);
    createChecker(160, 80);
```

Could translate to
```
called randomInteger:
pass value:
with:
max as number
return floor of random number * max

with:
checkboxes as undecided

give checkboxes:
from board:
elements called input

called createChecker:
work on:
with:
range as number
min as number

with:
time as number

give time:
result of randomIntegr + min
with:
range from range

repeat:
after time * 1000

with:
randomBoxInteger as number

give randomBoxInteger:
result of randomIntegr
with:
length of checkboxes

// tbd

finish work
```

Just figuring out a translation to that schema is super interesting as it already implies a lot of functionality of the potential language.

CC BY-NC-SA 4.0