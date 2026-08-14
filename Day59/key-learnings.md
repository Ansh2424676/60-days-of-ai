# Day 9 — Key Learnings

## 1. Structured Testing Is Important

A feature may work correctly with a normal input but still fail when it receives different or unexpected inputs.

Creating a structured test matrix helped validate HireLens across different resume formats, job descriptions, validation cases, and user workflows.

---

## 2. Edge Cases Need Separate Testing

Testing the normal workflow alone is not enough.

During Day 9, important edge cases included:

- Empty job descriptions
- Job descriptions below the minimum required length
- Oversized resume files
- Invalid resume file types
- DOCX resumes
- Highly relevant job descriptions
- Unrelated job descriptions

This helped verify that HireLens handles invalid and unusual inputs appropriately.

---

## 3. Test Both High-Match and Low-Match Scenarios

A resume matching system should be tested with both relevant and unrelated job descriptions.

A Graphic Designer job description exposed a scoring issue where the match score could become incorrectly high.

Expanding the skills dictionary with design-specific tools and skills helped improve the distinction between relevant and unrelated roles.

---

## 4. Dynamic UI Values Should Use Real Application Data

The resume-to-job match progress indicator previously contained a hard-coded value.

This was identified during the Day 9 review and corrected so the visual progress represents the actual calculated match percentage.

This reinforced the importance of checking whether UI elements accurately reflect backend data.

---

## 5. Regression Testing Is Essential After Bug Fixes

Fixing one issue can unintentionally affect existing functionality.

After the Day 9 changes, the complete automated test suite was executed again:

```powershell
python -m pytest -q
