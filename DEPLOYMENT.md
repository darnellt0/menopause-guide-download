# MenoPause Resource Guide — Deployment & Recovery Record

_Last verified from connected systems: 2026-09-09_

## Canonical recovery source

- Repository: `darnellt0/menopause-guide-download`
- Primary branch: `master`
- Dedicated known-good recovery branch: `recovery/2026-09-09-known-good`
- Known-good guide baseline commit: `3aca62dea94127e8a63406949bcc0f1607e2ac98`
- Role: preserved/recoverable source for the MenoPause resource guide
- Do **not** confuse this repository with `darnellt0/menopause-unmasked-landing`, which is the separate February event landing page.

The recovery branch is pinned to the last guide-content commit immediately before deployment/recovery documentation was added. If `master` changes in the future and the live page needs to be reconstructed, use the recovery branch/commit unless a newer verified production commit is documented below.

## Original Manus location

The preserved page source declares the original canonical Manus URL as:

`https://menopauseguide.manus.space/guide`

This Manus URL should be treated as legacy/origin history, not as the preferred long-term production endpoint.

## Recreated production deployment

The recent Work rebuild was reported as being recreated for Netlify, with the following deployment targets:

- Hosting provider: Netlify
- Reported Netlify site URL: `https://menopause-resource-guide.netlify.app`
- Intended custom domain: `https://menopause.rent-a-president.com`
- Reported Work-side source repository/project name: `menopause-resource-guide`

### Verification status

The Netlify site/project, custom-domain binding, DNS records, and the Work-side `menopause-resource-guide` repository are **not yet independently verified through the currently connected account integrations**. They must not be treated as fully locked until Netlify confirms the live site/project and domain mapping.

## Production ownership rule

Once Netlify verification is complete, this file should be updated so exactly one production chain is authoritative:

`production URL -> Netlify site/project -> Git repository -> branch -> commit`

The preferred production URL should be the custom domain if it is correctly configured and HTTPS-valid. The Netlify `.netlify.app` URL should remain available as the platform fallback.

## Recovery procedure

If the production deployment is lost or misconfigured:

1. Start from branch `recovery/2026-09-09-known-good` (commit `3aca62dea94127e8a63406949bcc0f1607e2ac98`) in `darnellt0/menopause-guide-download`, unless a later verified canonical production commit is recorded above.
2. Preserve `index.html` and the `/assets` directory together.
3. Deploy the static site to the approved hosting project.
4. Verify the page renders correctly on both desktop and mobile.
5. Verify all images, links, downloads, and calls to action.
6. Verify HTTPS on the final production URL.
7. Verify the custom-domain DNS points only to the current production host.
8. Update this file with the exact host project, repo, branch, production commit, and domain records.

## Change-control notes

- Do not repurpose or overwrite `darnellt0/menopause-unmasked-landing`; it is a different project.
- Do not delete or move the recovery branch until a newer canonical production recovery point has been independently verified and documented here.
- Do not remove this recovery repository until a newer canonical production repository has been independently verified and documented here.
- Do not place API keys, DNS-provider credentials, Netlify tokens, or other secrets in this file or repository.
