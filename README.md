# 🧬 Interactive Bioinformatics Practical Tutorial

A zero-setup, fully interactive web application designed for undergraduate Microbiology students to perform core bioinformatics practicals. 

This tool transforms traditional static lab manuals into an engaging, step-by-step digital workbook. Students can follow procedures, check off tasks, record their observations, and export a cleanly formatted PDF report for grading—all directly within their web browser.

## ✨ Key Features

* **Zero Installation Required:** Hosted entirely on GitHub Pages. Students just click the link and start learning.
* **Interactive Checklists:** Step-by-step progress tracking for complex bioinformatics workflows.
* **Persistent Auto-Save:** Uses browser `localStorage`. If a student accidentally closes the tab or refreshes, their checked boxes and typed answers are instantly restored.
* **Built-in PDF Export:** A custom print stylesheet strips away the UI navigation and formats the student's inputs into a clean, printable PDF lab report.
* **Streamlined Submission:** Integrated button that directs students to a specific Google Form to easily upload their generated PDF for educator grading.
* **Mobile Responsive:** Built with Tailwind CSS to ensure the tutorial is readable and functional on desktops, tablets, and mobile devices.

## 🔬 Modules Covered

The tutorial is based on the NEP TYBSc Microbiology curriculum. Each experiment follows the familiar practical-journal layout: **Aim → Principle → Procedure → Observations & Result**. Each one also has key terms, "what you should see" checkpoints, troubleshooting tips, hints and ungraded self-check questions.

0. **Start Here:** What bioinformatics is, how the experiments connect, golden rules (DNA → blastn/DNA mode; protein → blastp/Protein mode) and workspace setup.
1. **Database Exploration (NCBI):** Primary vs secondary databases, plus Taxonomy and PubMed mini-tasks.
2. **Sequence Retrieval (FASTA):** Reading a GenBank record and saving sequences in FASTA format.
3. **Similarity Searching (BLAST):** Percent identity, query cover and $E$-value, and the 16S species/genus rule of thumb.
4. **Multiple Sequence Alignment (MSA):** Clustal Omega (EMBL-EBI Job Dispatcher), conserved and variable regions, and indels.
5. **Phylogenetic Tree Construction:** Phylogeny.fr One Click (NGPhylogeny.fr as backup) and reading a phylogram.

### 🧫 Microbiology scenarios

* **Scenario 1: 16S rRNA (whole-class thread).** It runs through Experiments 1–5: identify *S. aureus*, align it with *B. subtilis*, *E. coli* and *P. aeruginosa*, and test whether the tree recovers the Gram-positive/Gram-negative split.
* **Practice Scenarios (group mini-projects):** each group picks one and repeats the workflow on a new problem.
  * **2. mecA:** antibiotic resistance and horizontal gene transfer (DNA, then protein)
  * **3. Candida ITS:** fungal identification; is "*Candida*" one natural group? (DNA, with a tree)
  * **4. SARS-CoV-2 spike:** viral evolution, substitutions and indels (protein)
  * **5. Taq polymerase:** why Taq cannot proofread (protein)

See [`docs/COURSE_REVIEW.md`](docs/COURSE_REVIEW.md) for the full course review and the reasons behind each change.

## 🚀 How to Use (For Students)

1. Open the live link provided by your instructor.
2. Fill out your **Name, Class, and Roll Number** at the top of the page.
3. Follow the instructions on the left side of the screen, checking the boxes as you complete each task on the respective bioinformatics websites (NCBI, EBI, etc.).
4. Type your interpretations and data into the text boxes provided. (Your work saves automatically!)
5. After Experiment 5, open **Practice Scenarios** and choose the scenario your teacher assigned to your group.
6. When finished, click **Export as PDF** in the bottom left corner and save the file to your device.
7. Click **Submit Report** to open the submission form and upload your PDF.

## 🛠️ How to Deploy (For Educators)

If you wish to fork this project and use it for your own institution:

1. Fork this repository or copy the `index.html` file into a new GitHub repository.
2. Go to your repository **Settings** > **Pages**.
3. Under **Build and deployment**, set the **Source** to `Deploy from a branch`.
4. Select the `main` branch and click **Save**.
5. Within minutes, your interactive tutorial will be live at `https://[your-username].github.io/[repository-name]/`.
6. *Optional:* To change the submission destination, edit `CONFIG.formUrl` at the top of the `<script>` in `index.html`.

### Preparing the scenarios (each semester)

1. Run Scenarios 1–5 yourself once and keep the screenshots as your answer key. **Do not put answer keys in this repository:** the site is public, and students can read its source.
2. In `index.html`, fill in the `CONFIG.accessions` block with the records you chose:
   * one full-length mecC protein (Scenario 2)
   * one `NR_` ITS record per *Candida* species from BioProject PRJNA177353 (Scenario 3)
   * one complete Alpha, Delta and Omicron BA.1 spike protein (Scenario 4)

   Blank slots show "Ask your teacher", and students type in the accession you give them.
3. On the day, check that Phylogeny.fr is up; NGPhylogeny.fr is the backup.

### Editing content

All the course text lives in plain JavaScript objects (`MODULES`, `SCENARIOS`, `GLOSSARY`) near the top of the `<script>` in `index.html`. To edit a step, a question or a hint, change the text there; there is no HTML to rewrite. Keep existing input `id`s unchanged so students' saved answers are not lost.

## 💻 Tech Stack

* **HTML5:** Semantic structure.
* **Vanilla JavaScript:** DOM manipulation, local storage handling, and modal logic (No heavy frameworks!).
* **Tailwind CSS (via CDN):** Rapid, responsive, and modern styling.

## 📄 Credits & License

* **Developed by:** Vishal Bhoir.
* **Concept & Content:** Introductory Bioinformatics tutorials © 2026 by [Vishal Bhoir](https://linktr.ee/thebioway).
* **License:** This project is licensed under the **CC BY-SA 4.0** (Creative Commons Attribution-ShareAlike 4.0 International) license.
```eof

