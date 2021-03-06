# Publishing Digital Marketplace GOV.UK Frontend

## Bumping the release version

1. Checkout **master** and pull latest changes.

2. Run `nvm use` to ensure you are using the right version of Node.js and npm.

3. Run `npm install` to ensure you have the latest dependencies installed.

4. Create and checkout a new branch (`release-[version-number]`).
  The version number is determined by looking at the [current "Unreleased" CHANGELOG](../CHANGELOG.md) changes and updating the previous release number depending on the kind of entries:

  - `Breaking changes` corresponds to a `major` (1.X.X) change.
  - `New features` corresponds to a `minor` (X.1.X) change.
  - `Fixes` corresponds to a `patch` (X.X.1) change.

  For example if the previous version is `2.3.0` and there are entries for `Breaking changes` then the new release should be `3.0.0`.

5. Update [`CHANGELOG.md`](../CHANGELOG.md) "Unreleased" heading with the new version number.

6. Update [`package/package.json`](../package/package.json) version with the new version number.

7. Commit the changes to `CHANGELOG.md` and `package/package.json` with the commit message "Release [version number]".

8. Create a pull request and copy the changelog text.
   When reviewing the PR, check that the version numbers have been updated and the changelog

9. Once the Digital Marketplace GOV.UK Frontend pull request is approved, merge to **master**.

10. Create a release in the [GitHub interface](https://github.com/alphagov/digitalmarketplace-govuk-frontend/releases/new)
  - select the latest tag version
  - set "Digital Marketplace GOV.UK Frontend release v[version-number]" as the title
  - add release notes from changelog
  - publish release

A [Github Action](../.github/workflows) will detect this and push the release to NPM.
