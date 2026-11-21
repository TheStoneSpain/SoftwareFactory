# Publish your repository

Create an empty repository named `SoftwareFactory` under Oscar Rangel’s `TheStoneSpain` GitHub account, without adding a README or license. In a terminal, open the extracted project folder and run:

```bash
git init -b main
git add .
git commit -m "Prepare personal Maestro distribution"
git remote add origin https://github.com/TheStoneSpain/SoftwareFactory.git
git push -u origin main
```

Git uses your configured commit identity; no previous commit history or fabricated author history is included.

The README and installer already point to `TheStoneSpain/SoftwareFactory`. Keep LICENSE and the upstream credit. A suggested repository description is:

> File-based project context and delivery workflows for AI coding tools. Personal distribution of Maestro.

Hidden folders contain the framework and adapters, so upload using Git rather than dragging only the visible files into GitHub. GitHub Actions will run installation checks when you push.
