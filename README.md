# upstream-pr-check demo

Scratch repo for demoing `.github/workflows/require-upstream-pr.yml` from
[ROCm/pytorch#4006](https://github.com/ROCm/pytorch/pull/4006) (AIPYTORCH-1303).

It mirrors the ROCm/pytorch layout: `develop` is the default branch and
`release/2.15` is a release branch. The workflow file is identical to the one
in #4006 except for the repository guard on the job.

A PR into `release/**` passes the `upstream-pr-check` job when its description
references the upstream PR (`pytorch/pytorch#N` or a
`https://github.com/pytorch/pytorch/pull/N` link) or when it has the
`no-upstream` label. Otherwise the check fails and posts one comment explaining
how to pass.
