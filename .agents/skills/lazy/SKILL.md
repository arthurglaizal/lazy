---
name: lazy
description: The user does not want to do it by hand. Take the action you just suggested and do it yourself, end to end, or say exactly what to connect if a capability is missing. Use only when the user explicitly invokes `$lazy`.
---

# Lazy

The user is being lazy on purpose: they do not want to do it by hand. You do it. Be thorough, not lazy yourself.

## What to do

The task is whatever follows the command. If nothing follows, it is the action you most recently suggested, or the steps you just asked the user to perform. If you offered alternatives, take the one you recommended. If there is nothing identifiable to do, ask in one line and stop.

## First line

Before anything else, open with one short sentence in the user's language that confirms you are taking over and names the action in a few words. For example: "Got it, I'll do it myself: creating the GitHub repo and pushing the first commit." In French: « Ça marche, je m'en occupe : je crée le repo GitHub et je pousse le premier commit. » Then start right away. If you must ask something first (see below), put the question right after that sentence.

## How

1. **Find the cleanest way to do it yourself.** In this order: tools already available in this session (shell, file edits, connected MCP servers, browser or computer control); an official CLI or API that is already installed and signed in; then an official tool the project already uses. Prefer official, scriptable, reversible methods over clicking through a UI. Check the current documentation when unsure.
2. **Do it.** Perform the steps instead of describing them. Do not stop at a plan unless something blocks you.
3. **Check that it worked.** Run it, read the result, or look at the new state.
4. **Report in a few lines:** what you did, how you checked it, and what, if anything, is left for the user.

## When something is missing

If a capability is missing (MCP server not connected, CLI not installed, not signed in, missing access or permission):

- Do every part you can first.
- Then give the shortest exact setup: what to install or connect, the exact command or setting, and where to click. Recommend one option (official MCP server, then official CLI, then anything else). Check the current documentation for the exact command instead of relying on memory.
- Say what to send once it is set up, usually `$lazy` again, and stop.

Installing software or adding an MCP server changes the user's setup: propose it and ask before doing it yourself, unless they already asked for it.

## Always left to the user

Never do these, even under `$lazy`. Do everything around them and hand over only the single remaining step:

- typing passwords, 2FA codes, API keys, or payment details; signing in; creating accounts;
- solving CAPTCHAs; accepting terms or consents;
- paying or moving money.

## Ask first

`$lazy` authorizes the work, not every irreversible outcome. Ask once, in one line, before: sending a message or email, publishing or deploying to production, deleting data, pushing to a shared branch, spending money, or changing anything outside the current project. Skip the question only if the user's request already named that exact action. Group these confirmations into a single question.

Respect the session's permission mode and any refused tool call. Never work around a refusal.

## Style

- Reply in the user's language.
- Act, do not narrate.
- If it truly cannot be done from here (a physical action, no possible access), say so in one line and hand over the finished material (text, file, command) so the user's part is as small as possible.

Each invocation handles one request. Do not keep Lazy mode active afterward.
