# Build the Agent (FL-07)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  
**Code:** FL-07  

---

## 1. Core Job MVP Execution Log

The `Search-Intelligence-Auditor` agent was built and executed in the local environment using Claude's MCP tool suite (`Read`, `mcp_workspace_bash`, `mcp_workspace_web_fetch`).

* **Execution Flow:**
  1. Agent reads local dataset specifications via `Read`.
  2. Agent executes Python feature engineering and Random Forest model training via `mcp_workspace_bash`.
  3. Agent verifies target leakage assertion (`trend_direction` excluded).
  4. Agent exports playbook receipts to `work/outputs/action_playbook_metrics.json` and `action_playbook_queue.csv`.
  5. Agent verifies live deployed paper via `mcp_workspace_web_fetch`.

---

## 2. Live Tool Connection Evidence

```text
[Tool Call 1]: Read("/sessions/.../scripts/ml_utils.py") ────────► Verified Feature Columns
[Tool Call 2]: mcp_workspace_bash("python3 scripts/run_all.py") ─► Executed RF Model Training
[Tool Call 3]: mcp_workspace_web_fetch("https://manthansingh26.github.io/FLY_Manthan/") ──► Verified HTTP 200 OK
```

---

## 3. Build Iteration Log & Deviations

* **Iteration 1 (Initial Build):** Raw script hardcoded outputs to `/tmp`. *Deviation & Fix:* Updated path logic to resolve relative to `repo_root / "work" / "outputs"`.
* **Iteration 2 (Leakage Audit):** Tested adding `trend_pct` to feature matrix `X`. *Result:* Assertion triggered as expected; target leakage column successfully removed.
* **Iteration 3 (Export Receipts):** Added automated generation of `action_mix.png` chart and `action_playbook_metrics.json` receipts.
