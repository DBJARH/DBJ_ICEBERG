---
version: 0.5
# status markup, copy verbatim into the status column:
#   <b class="dbj_red">tbd</b>
#   <b class="dbj_yellow">doing</b>
#   <b class="dbj_green">done</b>
statuses:
  - tbd
  - doing
  - done
---

<style>
b.dbj_red, b.dbj_yellow, b.dbj_green { color:#000; padding:1px 6px; border-radius:3px; white-space:nowrap; }
b.dbj_red { background:#f4a6a6; } b.dbj_yellow { background:#f7e27a; } b.dbj_green { background:#a8dca8; }
</style>


| UID_TIMESTAMP | status | comments |
|---|---|---|
| 011-2026-NOV-15 | <b class="dbj_green">done</b> | Reverses row 006: folder renamed `quaified_it_jobs_agents` → [qualified_it_jobs_agents](../content/posts/qualified_it_jobs_agents/index.md), fixing the typo. `aliases: ["/posts/quaified_it_jobs_agents/"]` added to front matter so the old live URL still resolves. DBJ confirmed when asked. Uncommitted. |
| 006-2026-NOV-15 | <b class="dbj_green">done</b> | 11 post folders use underscores or capitals against the lowercase-hyphen majority: `BPT_Birth_In_One_Image`, `agile_bpt`, `before_driving_the_bpt_track`, `bpt_business_ship_manual`, `dbj_agentic_agile_manifesto`, `dbj_taxonomy_engineering`, `nodes_of_super_densities`, `not_zachman`, `observations_on_skills`, `quaified_it_jobs_agents`, `why_dbj_method`. Folder name is the URL slug, so renaming breaks links unless an alias is added. Low Not renamed: the folder name is the public URL, and posts link each other by root-relative `/posts/<slug>/`. Decide: keep, or rename with `aliases:` for the old slug and updated links. **DBJ: just leave it, as it is.** |
| 010-2026-NOV-15 | <b class="dbj_green">done</b> | [qualified_it_jobs_agents](../content/posts/qualified_it_jobs_agents/index.md) front matter now says `image: "qualified_it_jobs_agents.png"`, but the file in the folder is `quaified_it_jobs_agents.png` (no second l), so the cover is missing. Rename the file or change the front matter: DBJ to decide. Fixed 2026-11-15, uncommitted, by DBJ ruling: the image file renamed to `qualified_it_jobs_agents.png` to match the front matter. The folder name kept its typo at the time (row 006), later reversed (row 011) |
| 003-2026-NOV-15 | <b class="dbj_green">done</b> | [qualified_it_jobs_agents](../content/posts/qualified_it_jobs_agents/index.md) was front matter only. DBJ added a one-line body, committed 4e6c643. See row 010 for its cover image |
| 009-2026-NOV-15 | <b class="dbj_green">done</b> | Posts audit 2026-11-15 (42 posts, mechanical checks against CLAUDE.md only; findings are rows 003-008). Links: the 23 distinct `https://method.dbj.org` links in `content/` were checked against the portal source (aliases, explicit ids), not the live site. All resolve except `/cmm#levels` in [BPT_Birth_In_One_Image](../content/posts/BPT_Birth_In_One_Image/index.md), where the anchor is not on the /cmm/ page: changed to `/cmm/dbj_cmm.html#levels`, uncommitted. `https://method.dbj.org/index` in four-kinds-of-workflows is unverified. No post uses the portal anchors renamed on 2026-11-15. Hugo build not run |
| 008-2026-NOV-15 | <b class="dbj_green">done</b> | [post-hype-agents](../content/posts/post-hype-agents/index.md) had an H1 "Post Hype Agents" duplicating its title: removed 2026-11-15, uncommitted. [enterprise-ai-at-last](../content/posts/enterprise-ai-at-last/index.md) was a false positive: its H1 "LLM Enterprise Concept" is not the title, left as is. |
| 007-2026-NOV-15 | <b class="dbj_green">done</b> | 31 posts have no `version:` key (SHOULD, not MUST): `BPT_Birth_In_One_Image`, `agile_bpt`, `ai-history`, `ai-or-iceberg`, `bpt-operating-model`, `bpt_business_ship_manual`, `c-dbj-error-concept-revisited`, `crufty-ai`, `dbj_taxonomy_engineering`, `durable-execution`, `ea-is-an-instrument`, `enterprise-ai-at-last`, `fake-it-until-you-make-it`, `feature-not-a-bug`, `four-kinds-of-workflows`, `in-the-era-of-ai-slop`, `incompetence-is-out-of-hand`, `language-layer-does-not-matter`, `modular-monolith-for-mainframe`, `most-valuable-architecture`, `nodes_of_super_densities`, `not_zachman`, `observations_on_skills`, `optimal-implementation`, `platos-cave`, `post-hype-agents`, `quaified_it_jobs_agents`, `superplane`, `the-danger-kruger-peak`, `tonyhoare`, `why-cmm-onboarding`. Posts are in [content/posts](../content/posts/). Low Fixed 2026-11-15, uncommitted: `version: 0.1` added after `date:` in all 31, other keys untouched. 0.1 is my choice, change if you want another value. |
| 005-2026-NOV-15 | <b class="dbj_green">done</b> | Tag case variants, CLAUDE.md says reuse an existing tag: `AI` (21 posts) vs `ai` ([ani-is-not-agi](../content/posts/ani-is-not-agi/index.md)); `TOGAF` ([ai-or-iceberg](../content/posts/ai-or-iceberg/index.md), [bpt-one-pager](../content/posts/bpt-one-pager/index.md), [not_zachman](../content/posts/not_zachman/index.md), [why-cmm-onboarding](../content/posts/why-cmm-onboarding/index.md)) vs `togaf` ([why_dbj_method](../content/posts/why_dbj_method/index.md)); `Taxonomy` ([not_zachman](../content/posts/not_zachman/index.md)) vs `taxonomy` ([dbj_taxonomy_engineering](../content/posts/dbj_taxonomy_engineering/index.md)). Low Fixed 2026-11-15, uncommitted: `ai` to `AI` in ani-is-not-agi, `togaf` to `TOGAF` in why_dbj_method, `taxonomy` to `Taxonomy` in dbj_taxonomy_engineering. |
| 004-2026-NOV-15 | <b class="dbj_green">done</b> | [feature-not-a-bug](../content/posts/feature-not-a-bug/index.md) starts with a UTF-8 BOM and CRLF line endings. Hugo tolerates it; it is noise in git. Low Fixed 2026-11-15, uncommitted: BOM removed. CRLF left as is: 34 of 42 posts have it and the git blobs are LF. |
| 002-2026-SEP-24 | <b class="dbj_green">done</b> | Christensen diagram in [bpt-balances-ai-speed](../content/posts/bpt-balances-ai-speed/index.md) is credited by name only: no source URL found. DBJ: That is good and enough. |
| 001-2026-SEP-24 | <b class="dbj_green">done</b> | New post [bpt-balances-ai-speed](../content/posts/bpt-balances-ai-speed/index.md) by CWR: agentic AI moves the cost bottleneck to specification and verification; BPT balances it. DBJ to review and check on localhost (`hugo server --minify`) |

---
<br/>
<br/>
<br/>
<br/>
DBJ_VERTICAL_KANBAN | &copy; 2026 by dbj@dbj.org | MIT License
