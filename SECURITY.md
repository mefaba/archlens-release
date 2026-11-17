# Security

ArchLens runs AI agents on your computer, serves a local web page and API, opens files in your editor, and imports packages that other people made. If you find a way around one of its protections, please report it privately.

## Reporting a vulnerability

Please do not open a public issue. Instead, go to this repository's **Security** tab and choose **Report a vulnerability**. Describe what you found, how to reproduce it, and what an attacker could do with it.

Only the latest release is supported.

## What to report

For example:

- A package or document that runs code, reads files or reaches the network when it is imported or opened.
- A generation job whose agent can write outside its workspace, or change a source repository.
- A web page, or another computer, that can use ArchLens's local API without being allowed to.
- A way to start a program other than the chosen editor or the default app when a source file is opened.
- Credentials, or paths on your computer, that end up in a visualization, a package or a response.
