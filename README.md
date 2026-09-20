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

The tutorial guides students through five core bioinformatics experiments based on the NEP TYBSc Microbiology curriculum:

1. **Database Exploration (NCBI):** Navigating primary/secondary databases and understanding tools like PubMed, BLAST, and PDB.
2. **Sequence Retrieval (FASTA):** Searching GenBank and retrieving nucleotide sequences in the universal machine-readable FASTA format.
3. **Similarity Searching (BLAST):** Using NCBI BLAST to calculate sequence similarities, $E$-values, and percent identities.
4. **Multiple Sequence Alignment (MSA):** Using EBI Clustal Omega to align $\ge 3$ sequences to find conserved functional sites and evolutionary variations.
5. **Phylogenetic Tree Construction:** Utilizing Phylogeny.fr to visualize evolutionary relationships and genetic divergence via cladograms.

## 🚀 How to Use (For Students)

1. Open the live link provided by your instructor.
2. Fill out your **Name, Class, and Roll Number** at the top of the page.
3. Follow the instructions on the left side of the screen, checking the boxes as you complete each task on the respective bioinformatics websites (NCBI, EBI, etc.).
4. Type your interpretations and data into the text boxes provided. (Your work saves automatically!)
5. When finished with all 5 modules, click **Export as PDF** in the bottom left corner and save the file to your device.
6. Click **Submit Report** to open the submission form and upload your PDF.

## 🛠️ How to Deploy (For Educators)

If you wish to fork this project and use it for your own institution:

1. Fork this repository or copy the `index.html` file into a new GitHub repository.
2. Go to your repository **Settings** > **Pages**.
3. Under **Build and deployment**, set the **Source** to `Deploy from a branch`.
4. Select the `main` branch and click **Save**.
5. Within minutes, your interactive tutorial will be live at `https://[your-username].github.io/[repository-name]/`.
6. *Optional:* To change the submission destination, edit the Google Forms URL inside the `openGoogleForm()` JavaScript function in `index.html`.

## 💻 Tech Stack

* **HTML5:** Semantic structure.
* **Vanilla JavaScript:** DOM manipulation, local storage handling, and modal logic (No heavy frameworks!).
* **Tailwind CSS (via CDN):** Rapid, responsive, and modern styling.

## 📄 Credits & License

* **Developed by:** Microbiology Department, L. D. Sonawane College, Kalyan.
* **Concept & Content:** Introductory Bioinformatics tutorials © 2026 by [Vishal Bhoir](https://linktr.ee/thebioway).
* **License:** This project is licensed under the **CC BY-SA 4.0** (Creative Commons Attribution-ShareAlike 4.0 International) license.
```eof

