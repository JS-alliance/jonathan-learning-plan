Making Commits
==============

Your message should include what change is being done and why.

Re-establishing the context of a piece of code is wasteful. We can’t avoid it completely, so our efforts should go to reducing it [as much] as possible. Commit messages can do exactly that and as a result, a commit message shows whether a developer is a good collaborator.


[Great guide on commit messages](https://chris.beams.io/posts/git-commit/#seven-rules)
[Create Atomic Commit Messages](https://www.freshconsulting.com/atomic-commits/)

In order to create a useful revision history, teams should first agree on a commit message convention that defines at least the following three things:

* __Style.__ Markup syntax, wrap margins, grammar, capitalization, punctuation. Spell these things out, remove the guesswork, and make it all as simple as possible. The end result will be a remarkably consistent log that’s not only a pleasure to read but that actually does get read on a regular basis.

* __Content.__ What kind of information should the body of the commit message (if any) contain? What should it not contain?

* __Metadata.__ How should issue tracking IDs, pull request numbers, etc. be referenced?


The seven rules of a great Git commit message
--------------------------------------------

* Separate subject from body with a blank line
* Limit the subject line to 50 characters
* Capitalize the subject line
* Do not end the subject line with a period
* Use the imperative mood in the subject line
* Wrap the body at 72 characters
* Use the body to explain what and why vs. how