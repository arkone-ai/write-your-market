# Write your market

Write down who you sell to as one file, `market.yml`, then test it on twenty companies before any list is built. It runs in the Claude or ChatGPT chat you already use, and there is nothing to install.

From THE 100K, a free programme by ArkOne: [arkone.ai/100k/dubai](https://arkone.ai/100k/dubai)

## What you leave with

- **`market.yml`:** one sentence of who you sell to, its edges, and a line saying why each edge is there.
- **A table of twenty companies:** each one marked keep or strike, with the edge that decided.

A good file passes one test. A stranger could read it and strike the wrong companies from a list without asking you anything.

## The seven steps

The example column follows an invented business: a six-person Dubai firm that installs and services commercial kitchens.

| Step | What you do | Example |
|---|---|---|
| **1. Write the sentence** | One line of who you sell to. Not a paragraph | Independent restaurants and cafés in Dubai and Sharjah that need a kitchen installed or serviced |
| **2. Give it edges** | Size as a range of staff. Sector in the words a company uses about itself, never the label a directory gave it. The places you can actually serve | 5 to 50 staff. Runs its own restaurant or café. Dubai and Sharjah |
| **3. Name who is never contacted** | Companies that fit every edge and still must not hear from you, each with a reason | Current service customers, other kitchen installers, anyone who asked to stop |
| **4. Save it as a file** | One field per edge, each with a line saying why it is there | [`example/market.yml`](example/market.yml) |
| **5. Run it over twenty companies** | Paste in twenty you know. A table comes back: company, keep or strike, the edge that decided. Nothing is changed yet | [`example/companies.csv`](example/companies.csv) |
| **6. Change the file, not the row** | Where you disagree, fix the edge and run it again. For a case that sits on the line, rule once and write the ruling into the file | A café by day that is a catering kitchen by night |
| **7. Read the strike rate** | Read the companies the file keeps and count how many you would throw out by eye. More than a handful means the sentence is loose | Tighten the edge that let them in |

## Run it in the chat you already use

This works in Claude or ChatGPT, on the free plan or a paid one.

1. **Open a new chat** and paste everything in [`prompt.txt`](prompt.txt).
2. **Answer one question at a time.** When it asks about size, give a range of staff, such as 5 to 50. Say "mid-sized" and it will ask you for numbers.
3. **Copy the file it shows** into a plain text file and save it as `market.yml`. A chat app shows the file as text for you to copy.
4. **Paste twenty companies,** one per line: the name, what the company says it does, where it is, and roughly how many staff.
5. **Read the table.** Where you disagree, tell it which edge to change, then ask it to run the twenty again.

To practise first, answer with [`example/business.csv`](example/business.csv) and paste [`example/companies.csv`](example/companies.csv). Then compare with [`example/expected.csv`](example/expected.csv): a good file keeps 11 and strikes 9, and four of the twenty need a ruling from you.

## The skill: the same seven steps, guided

`prompt.txt` does the job in one message. The skill walks you through each step, pushes back on vague answers, and stops at each case that needs your ruling.

| You use | Do this |
|---|---|
| **ChatGPT** | Paste [`skill/chatgpt-instructions.txt`](skill/chatgpt-instructions.txt) into your custom instructions, into the instructions of a Project, or as the first message of a chat. It is under 1,500 characters |
| **The Claude app** | If your plan lets you add skills, zip the folder [`skill/skills/write-your-market`](skill/skills/write-your-market) and upload it in your settings. If not, paste [`SKILL.md`](skill/skills/write-your-market/SKILL.md) as the first message of a chat |
| **Claude Code** | Run the two commands below. Claude Code then saves `market.yml` straight into your folder |

```
/plugin marketplace add arkone-ai/write-your-market
/plugin install write-your-market@write-your-market
```

Or copy the skill in by hand:

```bash
git clone --depth 1 https://github.com/arkone-ai/write-your-market /tmp/wym \
  && cp -R /tmp/wym/skill/skills/write-your-market ~/.claude/skills/ \
  && rm -rf /tmp/wym
```

## Your turn

Start from [`your-market.yml`](your-market.yml), the blank template. Every field has a comment saying what goes in it.

## The files

| File | What it is |
|---|---|
| [`prompt.txt`](prompt.txt) | The full prompt, as shown in the session |
| [`your-market.yml`](your-market.yml) | A blank template for your own market |
| [`example/market.yml`](example/market.yml) | What a finished file looks like, rulings included |
| [`example/business.csv`](example/business.csv) | The answers for the invented business |
| [`example/companies.csv`](example/companies.csv) | Twenty invented companies, messy on purpose: bands next to counts, a directory label that disagrees with what the company says |
| [`example/expected.csv`](example/expected.csv) | The verdict a good file gives each of the twenty, and the edge that decided |
| [`skill/`](skill/) | The skill for Claude, and the plain-text version for ChatGPT |

## Before you paste anything

This step needs only company names, what each company says it does, where it is and how big it is. That is all public. Leave out the names, emails and phone numbers of people. This step needs none of them.

Every business and company in `example/` is invented.

## Licence

MIT. See [LICENSE](LICENSE).
