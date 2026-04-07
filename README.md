# CV — Dr. Dhruv Kumar

## Repository Structure

```
CV/
├── anrf/                       # ANRF Bio-Data (primary, actively maintained)
│   ├── main_CV_ANRF.tex        # Main LaTeX source — ALL edits go here
│   ├── main_CV_ANRF.pdf        # Compiled output
│   └── main_CV_ANRF.aux/log/out  # LaTeX build artifacts
├── normal/                     # Older CV version (not actively maintained)
│   ├── CV_Dhruv_kumar.tex
│   ├── CV_Dhruv_kumar.pdf
│   └── res.cls
└── README.md
```

## How to Compile

```bash
cd anrf/
pdflatex main_CV_ANRF.tex   # run twice to resolve cross-references
```

---

## How to Add a New Paper Entry

**File to edit:** `anrf/main_CV_ANRF.tex`

All publications are in the **Publications** section. There are four subsections, each with its own label prefix:

| Subsection | Label | Use for |
|---|---|---|
| `Journal Articles & Transactions` | `J\arabic*` | Journal papers and transactions |
| `Conference Papers` | `C\arabic*` | Full papers at main conference tracks |
| `Workshop Papers, Posters & Abstracts` | `W\arabic*` | Workshop papers, posters, extended abstracts, student research workshops |
| `Preprints (arXiv / SSRN)` | `P\arabic*` | Unpublished preprints only |

### Ordering Rule
All entries within each subsection are in **reverse chronological order** (most recent year first). Within the same year, order by the month of the venue (most recent month first).

### Entry Format

```latex
\item Author One, Author Two, and \textbf{Dhruv Kumar}. YEAR. Paper Title. In \textbf{Venue Name (SHORT YEAR)}, pages.
```

- Wrap **Dhruv Kumar**'s name in `\textbf{...}` always.
- Use `\textbf{Venue Name (SHORT YEAR)}` for the venue.
- For Best Paper Awards, append: `\award{Best Paper Award}`
- Page numbers are optional if not yet available.
- For preprints, the format is slightly different (no "In"):
  ```latex
  \item Author One and \textbf{Dhruv Kumar}. YEAR. Paper Title. \textbf{arXiv:XXXXXXX (YEAR)}.
  ```

### Which Section to Place a Paper In

- **Journal / Transaction** → `Journal Articles & Transactions`
- **Main conference track** (e.g., ACL, EMNLP, NeurIPS, WWW, ICSE, SIGCSE) → `Conference Papers`
- **Workshop** (venue contains "Workshop", "@", or "W" suffix, e.g., `LLM4Code@ICSE`, `CCGridW`, `NeurIPS Workshop`) → `Workshop Papers, Posters & Abstracts`
- **Poster or extended abstract** (venue contains "Poster", "EA", or "Abstract") → `Workshop Papers, Posters & Abstracts`
- **Student Research Workshop** (e.g., `NAACL SRW`) → `Workshop Papers, Posters & Abstracts`
- **arXiv / SSRN preprint** (not yet published at a venue) → `Preprints (arXiv / SSRN)`

### Step-by-Step Checklist

1. Identify the correct subsection (see table above).
2. Find the correct position within the subsection (reverse chronological by year, then by month).
3. Add the `\item` entry following the format above.
4. If the paper was previously listed as a **Preprint**, remove it from the `Preprints` subsection.
5. Compile with `pdflatex` (twice) and verify the output PDF.
6. Commit and push; update the PR if one is open.
