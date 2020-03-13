## Pull Request

> Q1: Why are readme's in github in the .md format? What is .md and why does github
  use it instead of .txt, .html .docx, or any other file format?

.md stands for Markdown. Markdown is used because its ubiquitous and light weight. It can be rendered into HTML and other file formats easily.

> Q2: Is the keyword "fixes" the only way to auto-close an issue from a PR 
  pull request). Is there other keywords that can accomplish the same thing?

  - close #X
  - closes #X
  - closed #X
  - fix #X
  - fixes #X
  - fixed #X
  - resolve #X
  - resolves #X
  - resolved #X

> Q3: Do you have to create a new PR EVERYTIME you want to close an issue,
  or is it possible to close multiple issues within a single PR? If so, 
  how?

closes #1, closes #2, closes #3; rest of commit message.
You can also resolve issues in the message by using the keywords and issue number.
Doing this fixes #2.
Heres a fix for #3.
close #4 is no longer a problem.
