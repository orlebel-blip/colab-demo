# colab-demo

A demo project for experimenting with Google Colab and GitHub.

## Creative ideas — three ideas and repeated objects

`creative_ideas.ipynb` asks for an everyday object and uses the OpenAI Responses API
with `gpt-6-luna` to suggest **exactly three unusual, practical ideas**, clearly
numbered **1, 2, and 3**. Keep entering objects in the same running cell until you
type `quit` (case-insensitive) to stop.

### Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/), choose **File > Upload notebook**,
   and upload `creative_ideas.ipynb` from this folder.
2. Use a Python 3 runtime; no GPU is needed.
3. Run the SDK installation cell. It installs or updates `openai` in the Colab runtime.
4. Run the next code cell. Enter your OpenAI API key at the hidden `getpass` prompt.
5. Enter an everyday object, such as `mug`, and read the three numbered ideas.
6. Enter another object at the next prompt; no cell rerun or key re-entry is needed.
7. Type `quit` to finish. Colab's stop button also interrupts the program.

The key is requested once per session. Each nonempty object makes one API request;
blank inputs and `quit` make none. The code requests a structured response containing
exactly three ideas, checks the result, and adds the numbering itself. If a reply
is refused or incomplete, it shows a friendly message and asks for another object.
Connection, quota, and general API errors also return to the object prompt;
an authentication error ends the session so you can rerun with a valid key.

You need an [OpenAI API key](https://platform.openai.com/api-keys), API billing/quota,
and access to `gpt-6-luna`. API usage may incur charges; a ChatGPT subscription
does not supply API credits.

### Keep your key private

- Enter the key only in the hidden runtime prompt, never in source code or chat.
- The notebook keeps the key in memory inside a function and does not print it,
  write it to disk, or put it in an environment variable.
- Error messages are generic; raw API exceptions and request details are not printed.
- Clear notebook outputs before saving, sharing, or committing, and disconnect and
  delete the Colab runtime when finished. Never commit keys or credentials.
- The object description is sent to OpenAI. Avoid entering private information.

For authentication errors, check your key. For quota errors, check API billing or
wait before retrying. For model errors, check your account's access to `gpt-6-luna`.

### Scope and validation

The notebook is saved without outputs. Local checks cover its structure, Python
syntax, repeated objects, numbering, blank inputs, stopping, and error handling
with simulated API responses. The project owner also confirmed a successful live
Colab test of three numbered ideas, repeated object input, and stopping with
`quit`. No runtime keys or live outputs are included.

See the official [Responses API text guide](https://developers.openai.com/api/docs/guides/text)
and [GPT-6 Luna documentation](https://developers.openai.com/api/docs/models/gpt-6-luna).
The response format follows the [Structured Outputs guide](https://developers.openai.com/api/docs/guides/structured-outputs).
