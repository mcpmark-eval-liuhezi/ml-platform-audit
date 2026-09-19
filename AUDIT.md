# ML Platform Pre-Flight Audit

**Date of check: 2026-09-19**

## Hugging Face credentials

- **Account login:** `lhz7891444`
- **Organizations:** No organization memberships are visible to the current authentication method.

The platform's shared Hugging Face token authenticates as the user account `lhz7891444`
(account ID `68805cebc41d25c21ef2183e`, account type `user`, no Pro plan). The token is a
personal access token with `write` role. The Hub reports no organization memberships for
this token, i.e. it sees no organizations.

## Model availability

- **Model:** [google-bert/bert-base-uncased](https://huggingface.co/google-bert/bert-base-uncased)
- **Status:** Available on the Hub.
- **Pipeline task:** `fill-mask`
- **Downloads:** 3236.2M
- **Likes:** 3364

The pinned model resolves on the Hub (library `transformers`, architecture `bert`,
110.1M parameters, license `apache-2.0`, last updated 19 Feb 2024), so the serving stack's
pin remains valid.

## Kubernetes inventory

The cluster returned **4 namespaces**. Findings, namespace by namespace:

| Namespace | Deployments | Pods |
|---|---|---|
| `default` | none | none |
| `kube-node-lease` | none | none |
| `kube-public` | none | none |
| `kube-system` | 2 | 2 |

### `default`
- **Deployments:** none running.
- **Pods:** none running.

### `kube-node-lease`
- **Deployments:** none running.
- **Pods:** none running.

### `kube-public`
- **Deployments:** none running.
- **Pods:** none running.

### `kube-system`
- **Deployments (2):**
  - `coredns` — 1/1 ready
  - `local-path-provisioner` — 1/1 ready
- **Pods (2):**
  - `coredns-576bfc4dc7-f24qm` — Running
  - `local-path-provisioner-6795b5f9d8-sqgb6` — Running

**Summary:** 4 namespaces exist, all `Active`. All workloads are concentrated in
`kube-system` (2 deployments, 2 pods, all healthy/Running). The `default`,
`kube-node-lease`, and `kube-public` namespaces contain no deployments and no pods.
No application workloads are running outside `kube-system`.
