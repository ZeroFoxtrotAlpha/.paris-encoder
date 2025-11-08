(ai slop)

Morse .paris Generator

A lightweight Python tool with a simple Tkinter GUI to convert plain text into a Morse code timing file (.paris), which is just a CSV renamed with the .paris extension.

This tool lets you:

Input any text.

Choose a Character WPM (actual symbol speed).

Choose a Farnsworth WPM (effective spacing speed).

Preview or export a .paris file suitable for Morse keyer testing, CW simulators, or signal-timing visualization.

🧰 Features

No external dependencies — only uses the Python standard library.

Custom Farnsworth spacing for slower effective speeds.

Human-readable output with header comments.

Interactive GUI built with Tkinter.

⚙️ Requirements

Python 3.7 or newer

Tkinter (included in most standard Python installs)

🚀 Usage

Run the program

python morse_paris_tool.py


Enter text in the “Text to encode” field.
Example:

PARIS


Set speeds

Character WPM: how fast individual dots/dashes are sent (e.g., 15)

Farnsworth WPM: the overall effective speed including spacing (e.g., 5)

Preview your Morse timing table with the “Preview” button.

Export using “Export .paris” to save a file such as:

PARIS.paris

🧩 Output Format

Each .paris file is a CSV-formatted table with metadata headers.

Example:

# Word: PARIS
# Character speed: 15 WPM
# Farnsworth spacing: 5 WPM effective timing
duration_ms,value
84,1
84,0
252,1
84,0
252,1
84,0
84,1
504,0
...


Columns:

duration_ms: the length of the signal (on/off) in milliseconds

value: 1 for key down (tone on), 0 for key up (off)

📖 Morse Timing Logic

A dot = 1200 / CharacterWPM ms

A dash = 3× dot length

Intra-element gap = 1 dot

Inter-character gap = 3 dots (using Farnsworth WPM)

Inter-word gap = 7 dots (using Farnsworth WPM)

This follows the standard PARIS word timing definition used in Morse code standards (1 PARIS word = 50 dot units).

💡 Example Use Cases

Creating training or testing files for Morse code keyers.

Measuring timing jitter in Morse code generation hardware/software.

Feeding timing data into oscilloscope or plotting scripts.

Serving as an intermediate format for audio or keying waveform generators.

📜 License

MIT License — free for personal or commercial use.
Created by ChatGPT (OpenAI) for educational and hobbyist use.
