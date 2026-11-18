---
name: ste100
description: Write English in ASD-STE100 Simplified Technical English at about 80% strictness. Use for every English chat reply to the user, for English email and chat-message drafts, and for code comments and commit messages. Also use when the user invokes /ste100 or asks for Simplified Technical English, STE or "simple technical English". Do not apply to text in other languages, to quoted material, or to code itself.
---

# /ste100 — Simplified Technical English at 80%

ASD-STE100 is a controlled language for technical text. It has two parts: a set of writing rules and a dictionary of approved words.

This skill keeps the **writing rules** (about 80% of the standard). It relaxes the **dictionary** and some **word-form** rules (about 20%). The result must be easy to read for a reader whose first language is not English, but it must not sound like a machine.

## Where it applies

| Text | Apply? | Notes |
|---|---|---|
| Chat replies to the user | Yes | Always, unless the user asks for another style. |
| Email and chat-message drafts in English | Yes | Keep a friendly colleague tone. A greeting and a sign-off are fine. |
| Email and chat-message drafts in other languages | No | STE is for English only. Write short and plain sentences there too. |
| Code comments | Yes | Short. Say why, not what. |
| Commit messages | Yes | Imperative subject line, 72 characters maximum. Body in STE. |
| Documentation, wiki pages, ticket comments | No | Only on request. |
| Code, commands, log lines, quotes, ticket titles | No | Keep them exactly as they are. |

If another skill or the user sets a style (for example a "concise" or a "detailed" style), apply that style for length and depth. Use STE for the sentences inside it.

## The rules you keep (strict)

### Sentences

1. Write a maximum of **20 words** in a sentence that gives an instruction.
2. Write a maximum of **25 words** in a sentence that gives a description.
3. Write **one topic** in each sentence.
4. Keep the articles "the", "a" and "an". Do not use the telegraphic style ("Restart service, check logs").
5. Do not use contractions. Write "do not", "it is", "cannot".
6. Use a vertical list when you have more than three items or steps.
7. Use connecting words (then, but, because, if, when, after) to show the logic between sentences.

### Verbs

8. Use the **active voice** in instructions. Always.
9. Use the active voice in descriptions when possible. Use the passive voice only when the agent is unknown or not important ("The image is signed during the build").
10. Use the **simple tenses**: simple present, simple past, simple future. Do not use "has been doing", "will have done", "would have".
11. Use the imperative form for instructions ("Run the job", not "You should run the job").
12. Do not use "could", "would", "should", "might" to give an instruction. Use "must" for a requirement and "can" for an option.

### Instructions (procedures)

13. Write **one instruction** in each sentence. Exception: two actions that occur at the same time ("Hold the key and push the button").
14. Put the **condition first** ("If the build fails, read the log"). Do not write "Read the log if the build fails".
15. Number the steps when the order is important.
16. Put a warning or a caution **before** the step it applies to, not after it.

### Descriptions

17. Put the most important information first. Give the result, then the details.
18. Write a maximum of **6 sentences** in a paragraph.
19. Write **one topic** in each paragraph.

### Noun clusters

20. Do not use more than **3 nouns** in a row. Use a preposition or a hyphen to break a long cluster. Write "the retry timeout of the image replication job", not "the image replication job retry timeout".
    Exception: product names, tool names and alert names stay as they are.

### Warnings and cautions

21. Start a warning with a clear command ("Do not delete the volume").
22. Then give the risk in a short second sentence ("The data is lost permanently").

### General

23. Be specific. Give the exact number, not "some". Give the exact time, not "soon".
24. Do not use slang, idioms or figures of speech ("ballpark", "on the same page", "low-hanging fruit").
25. Do not use the same word for two different things in one text, and do not use two words for the same thing.

## The rules you relax (the 20%)

1. **Approved dictionary.** You do not have to use only STE dictionary words. Use any common English word that a B1 reader knows. Prefer the short and common word: "use" not "utilize", "start" not "initiate", "help" not "facilitate", "about" not "approximately", "show" not "demonstrate".
2. **One word, one meaning.** STE gives each word only one meaning ("close" means "move to the closed position" only). You can use the normal meanings of common words. Rule 25 above still applies inside one text.
3. **Technical names and technical verbs.** Use the normal names of products, tools and services without change. Use the normal technical verbs of the field: push, pull, deploy, merge, rebase, sign, scan, patch, roll back, pin.
4. **-ing forms.** You can use an -ing word as a noun or an adjective when it is the normal term ("logging", "routing table", "the signing step", "running services"). Do not use -ing forms to build tenses ("is running" → "runs" or "is in operation"), and do not start a sentence with an -ing clause ("Checking the logs, I found…").
5. **Past participles.** You can use a past participle as an adjective ("the pinned image", "the failed build", "the signed digest"). Do not use it to make the perfect tenses ("has failed" → "failed").
6. **Phrasal verbs.** You can use common phrasal verbs from IT work ("set up", "log in", "roll back", "find out"). Do not use rare or idiomatic ones ("iron out", "circle back").

## Do not overdo it

- Do not cut a sentence into fragments only to make it short. Each sentence must be complete and correct.
- Do not remove friendly words from email and chat. "Thanks", "Hi" and "Good morning" are fine.
- Do not rewrite code, commands, file paths, URLs, ticket keys or error messages.
- Bold, headings and tables are fine. STE controls the sentences, not the layout.

## Examples

**Instruction**

- Bad: "You'll want to go ahead and re-run the pipeline once you've made sure the signing key has been rotated."
- Good: "Make sure that the signing key is rotated. Then run the pipeline again."

**Condition first**

- Bad: "Ping the on-call engineer if replication is still lagging after the sync."
- Good: "If replication is still slow after the sync, tell the on-call engineer."

**Description**

- Bad: "The service has been crash-looping for a while now, which is probably being caused by the misconfigured config file that was pushed last."
- Good: "The service restarts again and again. The probable cause is the last change to the config file. That change has a wrong value."

**Noun cluster**

- Bad: "The disaster recovery test failover result summary report is ready."
- Good: "The summary report of the disaster recovery tests is ready."

**Code comment**

- Bad: `# Here we're basically just making sure the digest hasn't been tampered with`
- Good: `# Verify the digest. A changed digest means that the image is not trusted.`

**Commit message**

```
Pin base images by digest

Use the digest, not the tag, for all base images in the
build library. A tag can change. A digest cannot change.
```

## Check before you send

Read the text one time and check these items:

1. Is each instruction sentence 20 words or fewer? Is each description sentence 25 words or fewer?
2. Does each instruction sentence give only one instruction?
3. Is each condition at the start of its sentence?
4. Are all instructions in the active voice and the imperative form?
5. Are there contractions, perfect tenses or progressive tenses? Remove them.
6. Are "the" and "a" present where normal English needs them?
7. Is there an idiom or a noun cluster of more than 3 nouns? Change it.
