# Job fit check

Rates a freelance job post as **apply**, **maybe** or **skip**, with a fit score, a short explanation and a list of red flags. Every check is logged in a Google Sheet.

The post is pasted into a form by hand. The tool does not access any job platform automatically, and that is intentional.

| Verdict | Red flags |
| --- | --- |
| ![Maybe](images/maybe.png) | ![Skip](images/skip.png) |

## Who decides what

- **Code checks the facts:** location restrictions, whether the client has ever hired, whether the job is already filled, payment verification, Connects needed vs available, client age, number of proposals, language requirements.
- **AI judges the fit:** which requirements match my real experience, what is missing, what looks risky.
- **Code checks the AI:** every match must quote the job post word for word. A hard red flag always means skip, whatever the AI says.
- **I make the final call.**

## From the first tests

- A developer job got **skip**: the code caught a location restriction buried in the middle of the description, and the AI noticed the required hours didn't fit my schedule.
- A desktop RPA job got **maybe, 65/100**: a good skill match, but 50+ proposals and many candidates already interviewed.
- The AI score varied slightly between runs on the same post (10 vs 15); the verdict did not, because code enforces it.

![Log](images/log.png)

## Built with

n8n form, JavaScript, Google Gemini, Google Sheets.
