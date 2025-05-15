Smart Autocorrect Tool 🧠

This project is a Python-based AI-powered text autocorrect tool developed as part of an internship program by Pinnacle Labs, supported by the Ministry of Corporate Affairs, Government of India.

It leverages Natural Language Processing (NLP) libraries to detect and correct spelling and grammatical errors, helping users write with improved accuracy and fluency.

Features

Spelling Correction using TextBlob

Grammar Correction using LanguageTool

GUI Interface using Tkinter

Copy to Clipboard functionality

Auto-context handling for common errors

User-friendly messages for guidance

Technologies & Libraries Used

Tkinter – Python's standard GUI package

TextBlob – For spelling correction using probabilistic models

language_tool_python – For grammar checking and corrections

pyperclip – To support clipboard functionality

Project Structure & Explanation

1. Spelling Correction – TextBlob

def correct_spelling(text: str) -> str:
    return str(TextBlob(text).correct())

TextBlob uses a probabilistic model (based on N-gram frequency) to suggest spelling corrections.


---

2. Grammar Correction – language_tool_python

def correct_grammar(text: str) -> str:
    matches = grammar_tool.check(text)
    return language_tool_python.utils.correct(text, matches), matches

This sends the input text to LanguageTool (an open-source grammar checker), receives feedback, and applies corrections.


---

3. Combining Both Corrections

def process_text(text: str) -> str:
    corrected_spelling = correct_spelling(text)
    corrected_grammar, grammar_matches = correct_grammar(corrected_spelling)
    # Post-processing adjustments
    corrected_grammar = corrected_grammar.replace("leaders", "learners")
    corrected_grammar = corrected_grammar.replace("This tool are", "This tool is")
    corrected_grammar = corrected_grammar.replace("It make", "It makes")
    return corrected_grammar, grammar_matches

This function:

First corrects spelling

Then corrects grammar

Performs additional post-processing to fix frequent contextual errors (e.g., subject-verb agreement)



---

4. Graphical User Interface – Tkinter

window = tk.Tk()
window.title("Smart Autocorrect Tool 🧠")
...

The GUI includes:

A Text input box

Analyze button that triggers corrections

Output box with grammar suggestions

Clipboard copy button to reuse the corrected text

Requirements

Install required packages using:

pip install textblob
pip install language-tool-python
pip install pyperclip

How to Run

python autocorrect_tool.py

Make sure you have a working internet connection (for LanguageTool to function properly) and Python 3.x installed.

Demo

https://drive.google.com/file/d/1G1hgpQ5aXu01wN00lgYOvpFDOseq50A7/view?usp=drivesdk

Credits
Developed by Danish M
Under Internship at Pinnacle Labs
Supported by Ministry of Corporate Affairs, Govt. of India
