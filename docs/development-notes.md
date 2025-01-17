# Testing

## Unit Testing

Unit testing is set up for svelte-lexical package using Jest and Testing Library
- pnpm -C packages/svelte-lexical test

## E2E (end-to-end) Testing
E2E testing is set up for playground package using playwright

### Running locally
- Start the playground demo 
  - <code>pnpm -C demos/playground dev</code>
- Move into the project directory 
  - <code>cd demos/playground</code>
- Run tests
  - All tests (chromium, firefox and safari): <code>pnpm playwright test</code>
  - Just chromium browser: <code>pnpm test-e2e:chromium</code>

### Running in GitHub Actions
- See .github/tests.yaml
- It picks up the latest version of svelte-lexical from npm, so dependent on that being updated (running locally picks the latest local changes though)
- Test results are uploaded to GitHub Actions artifacts

# Creating NPM package

## GitHub action
<code>.github/workflows/npm-publish.yaml</code> automatically publishes a new package on creation of release on GitHub.

It uses NPM to build and publish (PNPM is not used due to a bug).

## Steps for creating a new release

- bump up the version number
  - for example, `pnpm version 0.1.3`
- create a tag in GitHub
  - it will automatically trigger GitHub action for creating a package

# Commit Messages

Please use following tags in your commit message:

- feat (or feature)
- bug
- test
- build
- perf (or performance)
- refactor
- docs

It is recommended to refer to the issue, for example, #12. 
If you want to close the issue, use `fix` or `close`, for example, fix #12.  

Example: [feat] added functionality for task reminders, close #12


