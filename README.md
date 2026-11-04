# rabit e2e fixtures

Git fixtures for rabit's end-to-end CI job tests (`com.rabit.integration.cijob.triggerbuild` in rabit).
Each branch is one fixture; tests point at it through `application-it.yaml` (`IT_GIT_BRANCH` and friends).

| Branch | Layout | Used by |
|---|---|---|
| `vc2sf-metadata` | Metadata format at the repository root: `classes/` + `package.xml` | `Vc2SfStartBuildET` |

Conventions:
- One fixture per branch, named after the job type and the variant it exercises.
- Keep each fixture small and self-contained, so it validates against a clean Developer org.
- Tests only run validate-only (check-only) deploys, so nothing here is ever saved to an org.
- When a branch's contents change, update the fixture keys in rabit's `application-it.yaml`.
