# llm_tools
Large Language Model Tools for the UNIX command line

# About
This project is intended to house UNIX style command line tools that utilize LLMs, following the UNIX philosophy.

"The UNIX command line philosophy is to do one thing and do it well. It encourages the use of small, modular programs that each perform a single task, allowing users to combine them in powerful ways. This concept is known as the "UNIX philosophy"."

# Installation

```
pip install -r requirements.txt
```

Place any binary files in your path.

# Usage

Set your open ai api key:
```
export OPENAI_API_KEY=<key>
```

# Examples


## gptop

```
$ cat examples/cars.csv| ./gptop -o "show me japanese cars only"

honda,civic,2000,1000
```
```
$ cat examples/cars.csv| gptop -o "show sql statement to group by brand and sum price"

SELECT brand, SUM(price)
FROM table
GROUP BY brand;
```
```
$ cat examples/notes.md| gptop -o "from the following meeting notes, summarize action items for each meeting"

Action Items for Meeting 1:
- Move forward with proof of concept for GPT3.

Action Items for Meeting 2:
- Rework the app.
- Bob to provide guidance.
- Mick to mock up new prototype.

Action Items for Meeting 3:
- Mick to demo new prototype.
- Bob to provide guidance.
```

```
$ cat examples/notes.md| ./gptop -o "from the following meeting notes, summarize each meeting by date and display the sentiment of the meeting"
Meeting 1 (December 5th): Positive sentiment - decided to move forward with proof of concept.

Meeting 2 (March 10th): Neutral sentiment - discussed concerns about accuracy of new prototype and plans to rework the app.

Meeting 3 (March 15th): Positive sentiment - Mick demoed new prototype and Bob
gave guidance.
```

## gpt
```
$ echo "write me a short summary about robots" | gpt
```
