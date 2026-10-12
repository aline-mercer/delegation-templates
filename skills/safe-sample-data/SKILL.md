---
name: safe-sample-data
description: Creates or prepares sample, demo and test data that holds no real personal data or secrets but keeps a realistic structure. Use when building fixtures, seeding a demo, writing documentation examples, sharing a file or screenshot with a helper, or masking a real export before handing it to another tool or person.
metadata:
  author: aline-mercer
  version: "1.0"
---

# Safe sample data

Sample data leaks in boring ways. A real email address is left in a fixture, a screenshot shows another
tab, or a hidden sheet still holds the original. This skill produces data that is useful and safe to show.

## When to use

- Writing test fixtures, seed data, demo accounts or examples in documentation.
- Sharing a spreadsheet, a log or a screenshot with an AI tool, a contractor or a public issue.
- Masking a real export so someone can work on its structure.

## Rules

1. **Prefer reserved values over invented look-alikes.** Reserved values cannot belong to anyone:
   - Domains and email addresses: `example.com`, `example.org`, `example.net` (RFC 2606), such as
     `ana.ito@example.com`.
   - IP addresses: `192.0.2.0/24`, `198.51.100.0/24`, `203.0.113.0/24` (RFC 5737) and `2001:db8::/32` (RFC 3849).
   - US phone numbers: `555-0100` to `555-0199`, which are reserved for fictional use.
   - Payment cards: only the test numbers your payment processor publishes. Never a real card.
   - Keys and tokens: obvious placeholders such as `sk_test_REPLACE_ME` or `<API_KEY>`. Never a real or
     revoked key.
2. **Make names obviously fictional but realistic in shape.** Vary their length, their scripts
   (`José`, `李华`, `O'Brien`) and empty optional fields, so edge cases are still tested.
3. **When masking real data, keep the relationships.** The same person gets the same stand-in everywhere.
   Shift dates by a constant offset. Scale amounts by a constant. Swap values in; do not delete columns,
   because broken structure makes the sample useless.
4. **Label it.** Put `SAMPLE DATA — not real` in the file name, the first row or the header, and on any
   demo screen.
5. **Make it reproducible.** Generate with a fixed seed and keep the generator script next to the data,
   so the sample can be rebuilt instead of hand-edited.

## Steps

1. Ask what the data is for: a test, a demo, docs or sharing. Ask which fields and which edge cases must be present.
2. List every field that could identify a person or unlock something: names, emails, phones, addresses,
   IDs, account numbers, IPs, tokens, free-text notes, file paths with usernames.
3. Choose a replacement rule for each field (see Rules) and write the rules down.
4. Generate or transform the data with a script, using a fixed seed.
5. Run the leak check below before the data leaves your machine.

## Leak check

- [ ] Search the output for `@`, `http`, digit runs of 9 or more, `key`, `token`, `secret`, `password` and the
      real organisation's name. Every hit is reserved or a placeholder.
- [ ] Headers, footers, comments, hidden rows, columns and sheets, named ranges and file properties are clean.
- [ ] Images: EXIF and location data are removed. Screenshots show no other tabs, notifications, address
      bars, avatars or account names.
- [ ] Free-text fields, such as notes and descriptions, were rewritten, not just left as they were.
- [ ] Row counts and the main totals still behave like the original, if masking was the aim.
- [ ] The file is labelled as sample data.

If anything real cannot be removed without breaking the task, stop and say so. Do not share it "just this once".

---
Also works with [Octuo](https://www.tutuo.ai/en/octuo/?utm_source=skills&utm_medium=repo&utm_campaign=launch-v3), a personal assistant for macOS.
