# Course Review: Introductory Bioinformatics Practicals (UG Microbiology)

This review covers the interactive tutorial (`index.html`), the README and the
*Microbiology Scenarios for the Bioinformatics Practicals* guide (9 Oct 2026). The
goal is to make the course simpler and easier to follow for undergraduate
microbiology students, and to give them scenario-based practice for every module.

---

## 1. What already works well

- **The five experiments are in the right order.** Retrieve → BLAST → align → tree
  is the standard introductory workflow, and each step feeds the next.
- **No installation is needed.** Students can start on any phone or laptop, and
  their answers save automatically.
- **The PDF report and Google Form** make submission and grading simple.
- **Short tasks with checkboxes** suit beginners.

## 2. Problems found and how they were fixed

| # | Problem | Why it matters for UG students | Change made |
|---|---------|-------------------------------|-------------|
| 1 | No orientation. Students go straight into NCBI with no idea what bioinformatics is or how the experiments connect. | Students lose the "why" and treat each practical as a separate click-through exercise. | New **Start Here** module: a wet-lab ↔ dry-lab comparison table, a five-step pipeline diagram, golden rules and a setup checklist. |
| 2 | Each experiment used a different example (Candida ITS in Exp 2, unnamed sequences later), so there was no single story. | Students cannot see how the output of one experiment becomes the input of the next. | **Scenario 1 (16S rRNA)** now runs through Exp 1–5, using four fixed accessions. The question it answers: does 16S rRNA alone sort bacteria by Gram reaction? |
| 3 | Each experiment had only an objective, steps and questions, with no principle and no key terms. | Students meet terms such as E-value, query cover and indel with no definition. | Each experiment now follows the **practical-journal layout** students already know: **Aim → Principle (in simple words) → Procedure → What you should see → If something goes wrong → Observations & Result → Check yourself**. Terms are defined in one searchable **Glossary of Terms** (sidebar button, plus a link under each Principle) instead of repeating a Key Terms list in every experiment. |
| 4 | "Choose DNA" was hard-coded, with no blastn/blastp vs DNA/Protein rule. | Protein scenarios (spike, Taq, PBP2a) fail or give nonsense results in DNA mode. | A **DNA/protein table** sits in the golden rules, and every scenario states its BLAST program and Clustal mode. |
| 5 | The Clustal Omega link (`www.ebi.ac.uk/Tools/msa/`) is outdated. | Students land on a redirect or an error page. | Updated to `https://www.ebi.ac.uk/jdispatcher/msa/clustalo`. |
| 6 | Exp 5 said "cladogram", but Phylogeny.fr One Click draws a **phylogram**. | The branch-length question only makes sense for a phylogram, so the wording contradicts the question. | Principle corrected. It now explains phylogram vs cladogram and branch support. **NGPhylogeny.fr** is given as a backup. |
| 7 | The FASTA header example `>gi|...|...` is outdated (NCBI dropped GI numbers from headers in 2016). | Students think their header is "wrong". | The example now uses `>NR_118997.2 Staphylococcus aureus ...`. |
| 8 | Exp 1 listed "Protein Database (PDB)" as an NCBI resource and relied on an "All Resources" link that has moved. | Factually confusing, and the instruction can't be followed. | Students now use the database drop-down beside the NCBI search box. Primary vs secondary databases are explained, with Taxonomy and PubMed mini-tasks. |
| 9 | BLAST recorded only identity and E-value. | Identity without **query cover** misleads, especially with partial sequences such as D83363. | Query cover was added. Students search the curated **16S rRNA database**, and the page gives the 98.7% species / 94.5% genus rule of thumb. |
| 10 | Long answers were cut off in the PDF (textareas printed at a fixed 100 px). | Graders could not read full answers. | Textareas now print as full-height text blocks. Each experiment starts on a new page, and help boxes, quizzes and hints are left out of the PDF. |
| 11 | Exp 4 and 5 produced unreadable labels (long accession strings). | Students cannot tell which row or tip is which organism. | A step was added to **shorten FASTA headers** (`>S_aureus`, etc.) before aligning. |
| 12 | No self-check and no help when stuck. | Weaker students stall and copy. | Each experiment has 2 ungraded **Check yourself** questions with instant feedback, plus **hints** on the harder questions. |

Version 1's saved answers are kept: the original input ids (`m1-input-1` … `m5-input-2`)
and the storage key are unchanged.

## 3. How the scenarios were built in

| Scenario | Where it appears | Experiments practised | Mode |
|----------|------------------|----------------------|------|
| 1. 16S rRNA (Gram +/−) | Exp 1–5 (guided whole-class thread). Its five guided questions are spread across Exp 2–5. | 1–5 | blastn / DNA |
| 2. mecA and gene transfer | Practice Scenarios (group project) | 2, 3, 4 | blastn, then Protein |
| 3. Candida ITS | Practice Scenarios | 2, 3, 4, 5 | blastn / DNA |
| 4. SARS-CoV-2 spike | Practice Scenarios | 2, 3 (optional), 4 | Protein |
| 5. Taq polymerase | Practice Scenarios | 2, 3, 4 | blastp / Protein |

Each scenario page has: **the problem** (a short clinical or industrial story), **what
you will discover**, a sequence table with live NCBI/UniProt links, procedure steps
tagged with the experiment they practise, a checkpoint, observation fields and the
five guided questions, each with a hint.

Every experiment ends with "Practise this skill again in: Scenario …" so students
can see which scenario reinforces which skill.

**Answer keys were deliberately left out of the student page.** The site is public, so
anything in it, even hidden, can be read with "View source". The hints point students
towards the reasoning without giving the answer. Keep the answer key from your
scenarios guide, plus your own screenshots, offline.

Extra student-facing aids added to the scenarios:
- Scenario 4: Ctrl+F search strings (`AIHVSG` for H69/V70, `QPTNGVGY` for N501), so
  students can find positions without counting residues.
- Scenario 5: a simple domain map (5′→3′ exo / 3′→5′ proofreading / polymerase) for
  comparing the front, middle and end of the alignment.

## 4. Before each semester: teacher checklist

1. Run Scenarios 1–5 yourself and save screenshots. They become your answer key.
2. Fix the teacher-chosen accessions in the `CONFIG.accessions` block at the top of
   the `<script>` in `index.html`:
   - one full-length mecC protein (Scenario 2)
   - one `NR_` ITS record each for *C. albicans*, *C. tropicalis*, *C. parapsilosis* and
     *N. glabratus* from BioProject PRJNA177353 (Scenario 3)
   - one complete spike protein each for Alpha (B.1.1.7), Delta (B.1.617.2) and
     Omicron BA.1, with no runs of X (Scenario 4)

   Any slot left blank shows "Ask your teacher" plus a box where students record the
   accession you give them.
3. Check that Phylogeny.fr is up on the day; NGPhylogeny.fr is the backup.
4. Check that NCBI still shows version `.2`/`.1` for the Scenario 1 accessions.

## 5. Further recommendations (not yet implemented)

These need decisions from the department, so they were left out of the code:

1. **Suggested timetable** (2-hour practical slots):
   - Week 1: Start Here + Exp 1 + Exp 2
   - Week 2: Exp 3
   - Week 3: Exp 4 + Exp 5
   - Weeks 4–5: group scenario and a 5-minute group presentation of the tree or
     alignment
2. **Grading rubric** for the PDF (example, out of 20):
   - correct accessions and values recorded (6)
   - screenshots attached (4)
   - interpretation answers (6)
   - scenario guided questions (4)
3. **Screenshots inside the report.** At present screenshots are kept separately. A
   later version could let students attach images that print with the PDF.
4. **Offline fallback.** If NCBI or EBI is down, a small set of pre-downloaded FASTA
   files in the repository (for example `data/scenario1_16S.fasta`) would let the
   class continue with Clustal and the tree.
5. **Viva questions.** Each guided question works well as a viva question. Ask
   students to explain an answer in their own words rather than read it out.
6. **Accessibility and language.** For mixed-medium classes, consider a Marathi/Hindi
   glossary column next to the English terms.
