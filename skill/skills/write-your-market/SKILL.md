---
name: write-your-market
description: Walk the owner of a small business through writing down who they sell to as one file, market.yml, with its edges and a reason for each, then test it on twenty companies they know. Use when someone asks to define their market, their ideal customer or their target list, says they want to start outbound or build a list of companies to contact, or asks to "write down my market".
---

# Write your market

**The job:** the owner leaves with `market.yml`, a file that says who they sell to with every edge written down, and a table of twenty companies sorted by it. A stranger should be able to read the file and strike the wrong companies from a list without asking the owner anything.

**How to run it:** seven steps, in order. Ask one question at a time and wait for the answer. Never fill in an answer for the owner. Where an answer is vague, say what is vague and ask again.

## Step 1. The sentence

Ask: "Who do you sell to, in one sentence?"

- **One line.** If they give a paragraph, ask which line of it they would keep.
- **It names who, where and what they need.** "Independent restaurants and cafés in Dubai and Sharjah that need a kitchen installed or serviced" is the shape.

## Step 2. The edges

Ask for each edge in turn, and ask why it is there.

| Edge | Ask for | Push back on |
|---|---|---|
| **Size** | The smallest and the largest company that fits, as a number of staff | Words such as "mid-sized", "small" or "not the big ones". Each becomes a number with a reason |
| **Sector** | What a company that fits says it does, in its own words | A directory category. Ask what the company would write about itself |
| **Place** | The cities, regions or countries they can actually serve | "Anywhere". Ask where they have actually delivered |

## Step 3. Never contacted

Ask: "Who fits every edge and must still never hear from you?"

Offer the usual three if they stall: current customers, competitors, and anyone who has asked to stop. Each gets a reason.

## Step 4. The file

Write `market.yml` in this shape. Every edge has a `why` line.

```yaml
sentence: ""
size:
  staff_min:
  staff_max:
  why: ""
sector:
  keep: ""
  strike: ""
  why: ""
place:
  keep: []
  why: ""
never:
  - who: ""
    why: ""
rulings: []
```

- **Where a file can be saved** (Claude Code, or any tool with file access): save it as `market.yml` in the folder the owner is working in, and say where it is.
- **In a chat app:** show it in one code block and tell the owner to copy it into a plain text file named `market.yml`.

Read the file back to the owner in plain words, one edge at a time.

## Step 5. The dry run

Ask them to paste twenty companies they know: some they sold to, some they wish they had never chased. Name, what the company says it does, where, and staff (a band or a rough count is fine).

Return one table and change nothing in the file:

| Company | Keep or strike | The edge that decided |
|---|---|---|

- **Name the single edge that decided** each strike.
- **Mark a company "on the line"** when the file cannot decide it: a business that is half one thing and half another, a directory label that disagrees with what the company says it does, a band that crosses an edge. Do not guess these.

If they have no list to hand, offer the practice set: twenty invented companies in `example/companies.csv` of github.com/arkone-ai/write-your-market, with the invented business in `example/business.csv`.

## Step 6. Change the file, not the row

When the owner disagrees with a verdict, the file has a loose edge.

1. Ask which edge is wrong and what it should say.
2. For each company on the line, ask for a ruling: keep or strike, and why.
3. Write each change into the file. Rulings go under `rulings`, each with `case`, `decision` and `why`.
4. Show the new file and run the twenty again.

Never change a single verdict by hand. The row follows the file.

## Step 7. The strike rate

Ask the owner to read the companies the file keeps and count how many they would throw out by eye.

- **A handful or fewer:** the file is ready. The next step, listing every company in the market, can read it as its search.
- **More than a handful:** the sentence is loose. Go back to step 1 or 2 with the companies they threw out, find the edge that let them in, and tighten it.

## Rules for every step

- **Never ask for the names, emails or phone numbers of people.** This step needs only what companies say about themselves, where they are and how big they are.
- **Never invent companies for the list the owner is building.** The practice set is the only invented data, and it says so.
- **Never decide a case on the line for them.** The rulings belong to the owner. The file applies them every time after.
