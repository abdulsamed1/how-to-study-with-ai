---
purpose: Contains one source catalogue section.
read_when: When the named source catalogue section is needed.
depends_on:
  - ../governance/source-policy.md
---

# Coverage gaps


## Coverage gaps

- No verified primary source yet provides a practical statistical treatment for comparing noisy LLM evaluation results (P14.3 uses the labeled interim protocol). S69 ch. 32 §32.14 and ch. 33 §33.8 are mapped as practical coverage leads, not verified statistical methodology, and do not close this gap.
- Webhook signature verification and raw-request-body handling are covered for two providers by S67 (GitHub) and S68 (Stripe). The residual gap is provider-specific behavior beyond those two (other signature schemes, retry windows, ordering guarantees) and first-party implementation evidence for P8.4.
- F3 (Node.js Learn) is registered at landing level; the P3.5 event-loop page is now recorded in the F3 row (2026-10-21). Exact pages for P3.6 and P7.2 (diagnostics, testing, security) are still not recorded.
- OAuth and credential-lifecycle depth for P4.8b is only partly covered by S6 (MCP-specific); RFC 9700 and provider documentation remain to be read.
- No source measures the effect of human-review practices on the quality of AI-generated code; S37 is a small vendor benchmark and S40 and S41 are qualitative vendor and practitioner material.
- No verified evidence on the learning outcomes of review-first curricula — that is, of teaching a learner to delegate implementation and review it, rather than to write it. S43 is a vendor team's own review process and S44 measures skill formation during AI-assisted coding, not the outcomes of a review-first curriculum. Treat the hand-writing-versus-review rule as a design decision to be checked against the learner's own evidence, not as a rule a source has established.
- No pedagogical source set is currently registered for the new interaction blueprint. Treat P01–P14 as an operational design specification, not as empirically validated claims; register and verify primary or systematic-review sources before making stronger evidence claims about any principle.
- No verified ingestion/access-control lifecycle how-to yet for P12.2/P15.4 (permission inheritance, retention, deletion).
- Residual RAG depth gap: chunking, embedding, and reranking tuning beyond the Barnett FP taxonomy.
- Enterprise outcome numbers with independent provenance (narratives exist as vendor-reported leads).

Lessons must name these as gaps rather than cite them as evidence. Scope guard: nothing in these gaps authorizes ML training, model-building, or researcher topics — fill them only with GenAI-application engineering sources (journey rule 9).

- Kafka 4.4 official documentation remains a verification gate for P8.1/P8.5/P8.7: S72 search excerpts were found, but direct full-page retrieval failed on 2026-11-12. Re-open the exact Kafka design and consumer API pages and verify the selected client/version before teaching configuration or API details.
- Deep distributed-systems and architecture topics are now assigned to core or conditional units in Phases 5–10. Do not treat TOC-only Foundations of Scalable Systems chapters or specialist topics (full consensus implementation, deep CRDTs, multi-region active-active, full streaming-platform operations, Data Mesh) as verified implementation guidance until the exact source sections and project need are confirmed.
