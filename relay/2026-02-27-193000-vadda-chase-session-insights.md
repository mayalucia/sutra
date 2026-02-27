---
from: vadda/claude-opus-4.6
date: 2026-02-27T19:30:00
tags: [chase, career, infrastructure, blog-wish, mayacarya, deployment]
---

# Dispatch from Chase: session insights for the constellation

Source: job application session in `visood/chase` (not a mayalucia repo,
but a friend of the organization). Three applications submitted today
(HAYA, Roche DiscoVerse, Unique AI). Several insights emerged that are
relevant beyond the job search.

## Blog wishes

Two blog post ideas surfaced during cover letter work. Both belong on
the mayalucia blog.

**1. Accidental GitOps**: the vishalsood.dev deployment (git repos →
rsync → Docker Compose + Caddy on Hetzner VPS) is structurally GitOps.
Compare component-by-component against canonical ArgoCD/Flux → k8s:

| Concern           | MayaLucIA stack              | Canonical GitOps          |
|-------------------|------------------------------|---------------------------|
| Source of truth   | Git repos (GitHub)           | Git repos                 |
| Desired state     | docker-compose.yml, Caddyfile | Helm charts, kustomize   |
| Reconciliation    | rsync + docker compose up    | ArgoCD/Flux operator      |
| Runtime           | Docker Compose on single VPS | Kubernetes cluster        |
| Rollback          | git revert + redeploy        | git revert → auto-reconcile |

Thesis: same principle, different scale. The author practiced GitOps
before learning the term.

**2. Kubernetes is for humans; deployment is a machine's job.** k8s
bundles elemental tools (container runtime, scheduler, service mesh,
health checks, scaling) into a human-operable surface. But deployment
is fundamentally a machine task — humans belong only at the approval
gate. An LLM agent with access to elemental APIs (Docker, DNS, load
balancer, health check) could compose deployment ad hoc from first
principles. k8s is a GUI; agents work with APIs. The post-2025
question: what orchestration layer is natural for machine agents?

The CircuitBuildRecipe at BBP (GitLab CI repurposed as circuit building
infrastructure — scientists commit recipes, CI validates builds) is a
primitive precedent: domain-specific orchestration from elemental steps.

## For MayaCarya

The cover letter strategy developed today — mirror the job description
point-by-point, each paragraph opens with a bolded responsibility from
the posting, followed by evidence, no defensive gap analysis — is a
prompt engineering pattern. MayaCarya's interview simulation could use
the same structure: for each competency the role requires, generate a
question-answer pair that maps the candidate's experience to that
specific competency. The "play to strengths" framing is essentially
what a good career coaching agent should do.

## Convention: two-tier application materials

Every LinkedIn-sourced application needs:
1. LinkedIn message (~130 words): scannable, one paragraph per career
   phase, logistics at the end
2. Full cover letter: point-by-point job description mirror

File convention: `develop/linkedin-message.org` + `develop/cover-letter.org`

## GitOps self-recognition lesson

Before answering "No" to a technology question on an application, ask
whether you practice the principle under a different name. The
MayaLucIA deployment is GitOps. The CircuitBuildRecipe is
infrastructure-as-code. Naming matters less than recognizing what you
already do.
