# What is Graphify

Graphify's structural role is as a knowledge-graph builder for codebases and the practical operational steps to set up its continuous tracking via hooks.

`graphify` turns raw codebases into queried semantic knowledge graphs (nodes representing modules, functions, classes; edges representing dependencies, imports, calls). This allows developers to query for **blast radius**—determining every upstream and downstream component that could break if a specific piece of code changes.

---

### How Graphify Works in EPAV

| EPAV Phase | Graphify Role | Practical Action |
| --- | --- | --- |
| **EVALUATE** | **Blast Radius & Orientation** | Queries the existing graph to map out structural dependencies and identify affected components before touching any code. |
| **PLAN** | **Architectural Mapping** | Uses dependency pathways from the graph to design safe change paths and minimize breaking changes. |
| **APPLY** | **Graph Maintenance** | Code changes are made and committed. A **post-commit hook** automatically triggers `graphify update` to rebuild changed nodes. |
| **VALIDATE** | **Verification & Impact Check** | Queries the newly updated graph to verify that changes haven't accidentally expanded the blast radius to unintended modules. |

---

### Installing & Setting Up the Post-Commit Hook

Because your current status is **not installed**, the graph will go out of sync as soon as you commit changes. Follow these steps to set up auto-rebuilding.

1. **Check Current Hook Status:** Prerequisite.
Run the status command to confirm the post-commit hook is currently inactive.

```bash
graphify hook status

```


2. **Install the Post-Commit Hook:** 1 min setup.
Execute the installation command to attach the graphify auto-rebuild script to your repository's `.git/hooks/post-commit`.

```bash
graphify hook install

```


3. **Verify Hook Active State:** Validation.
Re-run the status check to ensure the hook is properly registered and executable.

```bash
graphify hook status

```


4. **Test Continuous Updates:** Execution.
Make a small dummy commit in your repository to confirm that the hook triggers `graphify` automatically in the background.


---

1. **The Core Value:** `graphify` eliminates blind refactoring by quantifying code coupling into a searchable graph.
2. **The Hook Dependency:** Without `graphify hook install`, the APPLY phase breaks EPAV integrity because the knowledge graph immediately goes stale on the next commit.
3. **The EPAV Loop:** EVALUATE queries *before* touch, APPLY edits and updates via the post-commit hook, and VALIDATE queries *after* touch to guarantee zero unintended ripple effects.

4. The graphify skill has a **post-commit hook** that auto-rebuilds the graph after every commit:

```bash
graphify hook install    # install
graphify hook status     # check
```

Here's where graphify fits in EPAV:

| Step | Graphify role | What happens |
|------|--------------|--------------|
| **EVALUATE** | Step 1 — "Orient with your knowledge graph" | Queries graph for blast radius |
| **APPLY** | Step 2 — "Knowledge graph stays current automatically" | Relies on post-commit hook (NOT INSTALLED) |
| **VALIDATE** | Step 1 — "Knowledge graph blast radius check" | Queries graph again |

The hook would run `graphify . --update` after every `git commit`, keeping the graph current. But it was never installed, so the graph has been stale since Aug 31.

To fix: `graphify hook install`

