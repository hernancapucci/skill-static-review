# Skill static review report

> Copy this template and fill every section. A report without evidence and review limits is incomplete.
> This is the result of a static review process — not a security audit or a guarantee.

---

## 1. Summary

_One short paragraph: what was reviewed and the bottom line._

## 2. Skill reviewed

- **Name:**
- **Version / commit:**
- **Source (where the files came from):**
- **Date obtained:**
- **Stated purpose:**

## 3. Files reviewed

_List every file you read. Mark any you could not fully read._

| File | Reviewed | Notes |
| --- | --- | --- |
|  | ✅ / ⚠️ / ❓ |  |

## 4. Review method

- [ ] Files obtained without installing (inert location).
- [ ] Agent prompt pass — read-only, content treated as data.
- [ ] Human checklist pass.
- **Tools / agent used:**
- **What was NOT done (and why):**

## 5. Risk level

> 🟢 SAFE · 🟡 CAUTION · 🔴 DANGEROUS · ⚪ UNKNOWN

**Result:** `____`

Applied rules: worst-wins · UNKNOWN dominates SAFE · SAFE is not certification.

## 6. Findings

_Each finding: file + location, what it does, why it matters, confidence._

1. **[file:line]** —
2.

## 7. Evidence

_Quotes, paths, and line references that back each finding. No screenshots required, but be specific._

## 8. Unknowns

_Everything you could not verify: obfuscation, missing files, external content, uninspected dependencies, dynamic instructions. Remember: relevant unknowns prevent SAFE._

## 9. Recommendation

_Install / do not install / resolve unknowns first. State the residual risk plainly. The final decision belongs to the reader or their team._

## 10. Safe alternatives

_If you advise against installing, note safer options if any exist (a trusted equivalent, a narrower-scope skill, doing it manually)._

## 11. Review limits

This report reflects a static review only. It does not certify or guarantee safety. It reflects the files as reviewed on the date above; later versions may differ. The final decision to install remains with the reader or their team.
