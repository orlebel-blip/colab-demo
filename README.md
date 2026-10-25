# colab-demo

A demo project for experimenting with Google Colab and GitHub.

## Creative ideas — first milestone

`creative_ideas.ipynb` asks for an everyday object and uses the OpenAI Responses API
with `gpt-6-luna` to suggest **one unusual, practical use** in a short paragraph.

### Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/), choose **File > Upload notebook**,
   and upload `creative_ideas.ipynb` from this folder.
2. Use a Python 3 runtime; no GPU is needed.
3. Run the SDK installation cell. It installs or updates `openai` in the Colab runtime.
4. Run the next code cell. Enter your OpenAI API key at the hidden `getpass` prompt.
5. Enter an everyday object, such as `mug`, and read the single suggested use.
6. To try another object, rerun that cell. Each run makes one API request.

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

This milestone has no extra features: one object in, one idea out. The notebook is
saved without outputs. Local checks validate its structure, Python syntax, and
request flow with a simulated API response. The project owner also confirmed a
successful live API call in Google Colab that returned one unusual, practical idea.
The runtime key and live outputs are not included in the repository.

See the official [Responses API text guide](https://developers.openai.com/api/docs/guides/text)
and [GPT-6 Luna documentation](https://developers.openai.com/api/docs/models/gpt-6-luna).
