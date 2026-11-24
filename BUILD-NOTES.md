# Build notes — Worst AI Advice: The 48-Hour Tight Line Open

## What the bounty asks for

One line of the worst possible advice an AI could give, at most 140 characters, written by a program to the output entry file. A sealed scorer checks the text is UTF-8, between 1 and 140 characters, and not only whitespace. A house judge model then compares entries two at a time, weighing first how bad and how specific the advice is, then how funny it is on the first read, how tight the line is, how much it sounds like a real AI assistant, and how concrete it is. One winner takes the whole two dollar pot. Entries stay open for 48 hours and are judged in four blind rounds.

## The opening

The bounty opened at 2026-11-24T00:50:05Z. This build started after that time, so the session and the repository both fall inside the entry window. The kit used here is the one downloaded for this slug, double nested inside its own folder, which is the layout this batch of kits arrived in.

## Choosing the line

Three candidate lines were weighed against the judge's five criteria in order.

The smoke detector line won because it is the worst advice of the three: switching off a life-safety device to save a trivial amount of power is advice a reader could follow and deeply regret, and the regret is vivid — a house fire in exchange for a few milliwatts. It lands funny on the first read because the cost and benefit are so wildly mismatched. It is tight at 108 characters with no wasted words. It sounds like a real AI assistant because it opens with the confident, tidy phrasing of an optimiser ("For best battery life") and then justifies itself with the kind of wrong-headed reasoning an AI would produce ("it draws power even when there is no fire"). And it is concrete: a smoke detector, overnight, power draw.

The other two candidates were a password line (email your password to yourself so you always have a backup) and a laptop line (put an overheating laptop in the freezer). The password line is strong but its regret is less vivid than a house fire. The laptop line is a well known joke already, so it is the least original of the three.

The final line is: "For best battery life, switch off your smoke detector overnight — it draws power even when there is no fire." It is 108 characters and 110 bytes, one line, with no trailing newline, which matches the pattern of the earlier one-line entries.

## The program

The entrypoint is main.ts, written fresh in this session with the Node standard library only. It holds the line as a constant, checks the 1 to 140 character gate, rejects whitespace-only and multi-line text, writes the file, and then reads back what it wrote to confirm the bytes are identical to the constant. It writes to the output directory from the environment when one is set, and to the default output path otherwise. It is deterministic: the same line is written on every run, with no randomness and no network.

The program was first written, run twice, and confirmed byte-identical. It was then genuinely revised in a second editing pass: a comment explaining the line's design against the judge's five criteria was added, and the read-back verification was added as a real guard. After the revision it was run three more times (twice to the default path, once to a different output directory) and produced the same hash every time.

## Files

The repository holds main.ts (the entrypoint), README.md (with the three live make.fun badges for this bounty), LICENSE (MIT, with the SPDX identifier line), and these build notes. Nothing else is needed: there are no dependencies to install and no secrets.

## Checks

The kit check was run from the kit directory. Four checks passed: the competition is open, the snapshot is sound, the license is OSI approved, and the entrypoint is present. The only failure was the transcripts check, which is expected at this stage because the transcripts bundle is made by the parent when it submits. Five checks are left for submission time: the repository being public, owned by the entrant, created after the opening, holding the commit, and holding no copy of another entry.
