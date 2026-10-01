# Question banks

## Table of contents

1. How to use these banks
2. The clear-answer test
3. Route B: requirements grill
4. Route B: bug-report grill
5. Route D: diagnosis round
6. Route D: guiding questions by weak area
7. Route E: change gate

## 1. How to use these banks

Pick and adapt questions; do not paste the whole bank. Put each round in
one `AskQuestion` call. Give 2 to 5 plausible options per question plus
"Other". Options must not signal which is correct: include at least one
tempting wrong option, keep them similar in length, and never mark one as
recommended.

## 2. The clear-answer test

An answer passes only if all four hold:

1. **Own words:** not a copy of an earlier AI message or document.
2. **Meets the target LOD:** as defined in the LOD table (lod.md) for the
   component in question.
3. **Names the trade-off:** what is given up or risked.
4. **Falsifiable:** says what result or observation would show it is wrong.

If an answer fails, ask one follow-up aimed at the missing part. Do not
fill the gap yourself.

## 3. Route B: requirements grill

- What do you want to be true when this is done?
- What goes in, and what should come out? (format, a sample value)
- What must it not do, or what is out of scope?
- Which constraint matters most here: speed, accuracy, simplicity,
  privacy, or time you have left?
- How will you check it worked?

## 4. Route B: bug-report grill

- What exactly did you run? (command, task name, or button)
- What did you expect to happen?
- What happened instead? Paste the full error, not a screenshot crop.
- Did it ever work? What changed since then?
- What have you already tried, and what did each attempt show?

## 5. Route D: diagnosis round

- In one sentence, what are you trying to decide?
- What is your current guess, even if unsure?
- Where exactly are you stuck: not knowing the options, not knowing how to
  compare them, or not knowing what the result would mean?
- What have you read or tried so far?

## 6. Route D: guiding questions by weak area

**What each comparison proves (ablation logic):**
- Which one thing differs between these two setups?
- If setup X beats setup Y, what is the only thing that could explain it?
- What result would mean the new component added nothing?

**Freezing rules before testing:**
- If you tuned this value on the test forms, what would the final number
  really be measuring?
- Which forms has this value been chosen on, and which forms has it never
  seen?
- What would a sceptical examiner say if you changed it after seeing
  results?

**Statistics:**
- Out of the flags raised, how many were real errors? Out of the real
  errors, how many were flagged? Which of those is precision?
- Two setups were run on the same fields. Why does that pairing matter for
  the test you choose?

**VLM behaviour:**
- On which kinds of box has the model been confidently wrong?
- Why would "unsure" not catch those cases?
- Which rule in the pipeline stops a confident wrong answer from being
  accepted?

**Defending AI-written material:**
- Without looking, what does this section claim?
- Which part of it would you struggle to explain to your supervisor?
- If you had to cut it in half, what would you keep and why?

## 7. Route E: change gate

Ask these, going only as deep as the component's target LOD:

- Why is this change needed? What problem does it fix?
- What else does it affect: which tickets, files, results or essay
  sections?
- What could break, and how would you notice?
- How will you know it worked? Name the check.
- What alternatives did you consider, and why this one?
- (LOD 350 and above) Which other components does it connect to, and what
  changes for them?
- (LOD 400 and above) Walk through the lines or steps that change.

After the gate opens, log the change with the user's answers summarised in
their own words.
