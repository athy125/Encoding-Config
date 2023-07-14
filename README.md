# Encodings and Data Formats

This repository contains information about various encodings and data formats. It explores different formats, analyzes their advantages and disadvantages, and provides guidance on converting between them.

Please utilize modules exclusively from Python's standard library, unless specified otherwise in the exercise description.

## Task 1: XML and JSON

In this task, you will enhance the Joke and JokeGenerator classes to enable saving their attributes in XML or JSON representation.

### Task 1.1: XML Representation

Implement the `_get_xml_repr(self) -> etree.Element` method of the Joke class. It should return an lxml element representing the joke, with all attributes as subelements. The example below demonstrates a potential XML representation:

```xml
<joke>
    <text>Doctor: "So, you're telling me that you have a problem with one of your ears. Are you sure?" Me: "YES Doctor, I'm definite."</text>
    <author>VERBERD</author>
    <link>https://old.reddit.com/r/dadjokes/comments/rvzg8l/doctor_so_youre_telling_me_that_you_have_a/</link>
    <rating>1</rating>
    <time>04.01.22 17:16</time>
    <profanity_score>0</profanity_score>
</joke>
```

For aggregating and saving all jokes from the `reddit_dadjokes.csv` file, implement the `save_jokes_xml(self, outfile: str) -> None` method of the JokeGenerator class. This function should generate a well-formatted XML file, `reddit_dadjokes.xml`, containing all jokes as subelements of a new super element called `jokes`.

#### Outcome
* Implementation of `def _get_xml_repr(self) -> etree.Element`
* A file named `reddit_dadjokes.xml` containing all jokes from `reddit_dadjokes.csv` in XML format

### Task 1.2: JSON Representation

Similar to Task 1.1, this task requires saving the attributes of the Joke class using a JSON representation. Implement the `_get_json_repr(self) -> Dict` method of the Joke class, which should return a dictionary representing the joke attributes. Store the outcome of this method in the init method of the Joke class. The example below illustrates a JSON representation:

```json
{
    "author": "VERBERD",
    "link": "https://old.reddit.com/r/dadjokes/comments/rvzg8l/doctor_so_youre_telling_me_that_you_have_a/",
    "text": "Doctor: \"So, you're telling me that you have a problem with one of your ears. Are you sure?\" Me: \"YES Doctor, I'm definite.\"",
    "rating": 1,
    "time": "04.01.22 17:16",
    "profanity_score": 0
}
```

To combine and save all jokes from the `reddit_dadjokes.csv` file, implement the `save_jokes_json(self, outfile: str) -> None` method of the JokeGenerator class. This function should create a dictionary containing all jokes, with the indices from the `jokes` attribute list as keys and the individual JSON representations of the jokes as values. Save the resulting JSON representation in the file `reddit_dadjokes.json`.

#### Outcome
* Implementation of `def _get_json_repr(self) -> Dict`
* A file named `reddit_dadjokes.json` containing all jokes from `reddit_dadjokes.csv` in JSON format

### Task 1.3: Instantiating JokeGenerator with a JSON File

For this task, modify the `make_jokes_objects(self)` method of the JokeGenerator class to accept files containing jokes in a JSON representation. The method should still return a list of Joke objects containing all the jokes from the file. No changes outside the function should be necessary. If you were unable to complete Task 1.2, you can use the provided `example.json` as a sample input. If you successfully completed the task, please use your own `reddit_dadjokes.json` from the previous subtask.

#### Outcome
* Your implementation for `make_jokes_objects(self)`

## Task 2: Encodings

This task involves converting two files with different encodings into UTF-8. You will receive two files, `encoding_1.txt` and `encoding_2.txt`. One file is encoded in ISO 8859-1, and the other is encoded in ASCII.

For this exercise, you need to:

* Determine the encoding of each file.
* Convert both files to UTF-8 and save the output to a single file named `encoding_utf-8.txt`.

**Hint**: Once you determine the encoding of a file, you only need to read, write, and append to files using the Python standard library to perform the conversion.

#### Outcome
* A Python file named `task_2.py` containing the functions used to convert the encodings.
* A text file named `encoding_utf-8.txt` containing all jokes from `encoding_1.txt` and `encoding_2.txt` encoded in UTF-8.

## Task 3: Text Formats

CSV, JSON, and XML are three different text formats explored in this task. Each format has its advantages and disadvantages. Analyze and compare the formats to identify one advantage and one disadvantage for each:

a) XML:
   - Advantage: Provides a hierarchical structure and supports complex data relationships.
   - Disadvantage: XML files can be verbose and consume more storage space compared to other formats.

b) JSON:
   - Advantage: Offers a compact and human-readable format that is easily understandable.
   - Disadvantage: JSON lacks support for certain data types, such as dates, making it less suitable for representing structured information.

c) CSV:
   - Advantage: CSV is a simple and widely supported format, making it easy to import and export data across different systems.
   - Disadvantage: CSV lacks standardized schemas, leading to potential data inconsistency and ambiguity.

### Outcome
* Your answers to a) and b) in a separate text file named `task_3.txt`.

## Data Sources
`dadjokes_samples.txt`: https://www.kaggle.com/oktayozturk010/reddit-dad-jokes

`profanities.txt`: https://www.freewebheaders.com/full-list-of-bad-words-banned-by-google/
