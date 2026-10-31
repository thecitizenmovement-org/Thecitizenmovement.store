# Library bot routing — decided 2026-10-31

- **State is the determining factor.** The user names the state (name or
  abbreviation, e.g. "California", "CA", "Texas", "TX") and the bot loads
  that state's file from GitHub: `codes/<STATE>/...`, split by code title
  so no file approaches GitHub's 100 MB per-file limit.
- **Federal codes** are a separate top-level set: `codes/FEDERAL/...`
  (e.g. U.S. Code titles). A federal question loads the federal file,
  not a state file.
- **County does NOT pick the code file.** State law is the same
  statewide; county is context for local ordinances, filing office, and
  court location — a separate layer to be built later, not a code-file
  selector. A county name alone does not reliably identify a state
  (many county names repeat across states), so it is not used to infer
  state on its own.
- **No state given:** default to California, and label the answer as
  California so the user can correct it. (Movement base is California;
  user is in Tehama County.)
- **Answer labeling:** every local answer names the state, the code,
  and the source file, plus the general-information / not-legal-advice
  disclaimer. No Gemini call is made for a matched library/code answer.
- **Loading rule:** only the matched state's file (or the matched
  chapter) is loaded, never the whole multi-state library — that is
  what keeps answers instant.
