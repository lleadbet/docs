---
title: Contributing Guide
---

Excited about Apollo and want to make it better? We’re excited too. Read below to learn about different ways to contribute to the project.

## Issues

### Reporting bugs

If you encounter a bug, please file an issue on GitHub via the repository of the sub-project you think contains the bug. If an issue you have is already reported, please add additional information or add a 👍 reaction to indicate your agreement.

While we will try to be as helpful as we can regardless, please include the following to maximize the chances of a quick fix:

1. **Intended outcome:** What you were trying to accomplish when the bug occurred, and as much code as possible related to the source of the problem.
2. **Actual outcome:** A description of what actually happened, including a screenshot or copy-paste of any related error messages, logs, or other output that might be related. Places to look for information include your browser console, server console, and network logs. Please avoid non-specific phrases like “didn’t work” or “broke”.
3. **Reproduction:** A minimal reproduction of the issue that we can run. This is ideally in the form of a small application we can clone from GitHub, or a failing test sent in the form of a PR. The reproduction should contain as little code as possible to demonstrate the bug.

Creating a good reproduction really helps contributors investigate and resolve your issue quickly. In many cases, the act of creating a minimal reproduction illuminates that the source of the bug was somewhere outside the library in question, saving time and effort for everyone.

A good starting point for building reproductions are the "hello world" examples on the [developer home page](http://dev.apollodata.com):

  - [React Version](https://github.com/apollographql/react-apollo-error-template)
  - [Angular 2 Version](https://github.com/apollostack/frontpage-angular2-app)

### Suggesting features

Most of the features in Apollo were suggested by the community at some point in time. We welcome any ideas about how to make our project better for your use case. Unless there is overwhelming demand for a feature, it might not get implemented immediately, but please include as much information as possible that will help people have a discussion about your proposal:

1. **Use case:** What are you trying to accomplish, in specific terms? Often, there might already be a good way to do what you need and a new feature is unnecessary, but it’s hard to know without information about the specific use case.
2. **Could this be a plugin?** In many cases, a feature might be too niche to be included in the core of a library, and is better implemented as a companion package. If there isn’t a way to extend the library to do what you want, could we add additional plugin APIs? It’s important to make the case for why a feature should be part of the core functionality of the library.
3. **Is there a workaround?** Is this a more convenient way to do something that is already possible, or is there some blocker that makes a workaround unfeasible?

Feature requests will be labeled as such, and we encourage using GitHub issues as a place to discuss new features and possible implementation designs. Please refrain from submitting a pull request to implement a proposed feature until there is consensus that it should be included. This way, you can avoid putting in work that can’t be merged in.

Once there is a consensus on the need for a new feature, proceed as listed below under “Big PRs”.

## Small PRs

If there is a small change to be made, please feel free to open a PR right away with the fix or improvement. For this category of pull requests, there is no need to write a design first.

### Documentation fixes

Improving the documentation, examples, and other open source content can be the easiest way to contribute to the library. If you see a piece of content that can be better, open a PR with an improvement, no matter how small! If you would like to suggest a big change or major rewrite, we’d love to hear your ideas but please open an issue for discussion before writing the PR.

### Small bug fixes

For a small bug fix change (less than 20 lines of code changed), feel free to open a pull request. We’ll try to merge it as fast as possible and ideally publish a new release on the same day. The only requirement is, make sure you also add a test that verifies the bug you are trying to fix.

## Big PRs

This includes:

- Big bug fixes
- New features

For significant changes to a repository, it’s important to settle on a design before starting on the implementation. This way, we can make sure that major improvements get the care and attention they deserve. Since big changes can be risky and might not always get merged, it’s good to reduce the amount of possible wasted effort by agreeing on an implementation design/plan first.

1. **Open an issue.** Open an issue about your bug or feature, as described above.
2. **Reach consensus.** Some contributors and community members should reach an agreement that this feature or bug is important, and that someone should work on implementing or fixing it.
3. **Agree on intended behavior.** On the issue, reach an agreement about the desired behavior. In the case of a bug fix, it should be clear what it means for the bug to be fixed, and in the case of a feature, it should be clear what it will be like for developers to use the new feature.
4. **Agree on implementation plan.** Write a plan for how this feature or bug fix should be implemented. What modules need to be added or rewritten? Should this be one pull request or multiple incremental improvements? Who is going to do each part?
5. **Submit PR.** In the case where multiple dependent patches need to be made to implement the change, only submit one at a time. Otherwise, the others might get stale while the first is reviewed and merged. Make sure to avoid “while we’re here” type changes - if something isn’t relevant to the improvement at hand, it should be in a separate PR; this especially includes code style changes of unrelated code.
6. **Review.** At least one core contributor should sign off on the change before it’s merged. Look at the “code review” section below to learn about factors are important in the code review. If you want to expedite the code being merged, try to review your own code first!
7. **Merge and release!**

### Code review guidelines

It’s important that every piece of code in Apollo packages is reviewed by at least one core contributor familiar with that codebase. Here are some things to look for:

1. **Required CI checks pass.** If the tests don’t pass, there is no need to review the PR until they do.
2. **Simplicity.** Is this the simplest way to achieve the intended goal? If there are too many files, redundant functions, or complex lines of code, suggest a simpler way to do the same thing. In particular, avoid implementing an overly general solution when a simple, small, and pragmatic fix will do.
3. **Testing.** Do the tests ensure this code won’t break when other stuff changes around it? When it does break, will the tests added help us identify which part of the library has the problem? Did we cover an appropriate set of edge cases? Look at the test coverage report if there is one. Are all significant code paths in the new code exercised at least once?
4. **No unnecessary changes.** PRs shouldn’t come with random formatting changes, especially in unrelated parts of the code. If there is some refactoring that needs to be done, it should be in a separate PR from a bug fix or feature, if possible.
5. **Code has appropriate comments.** Complicated logic should be commented, or written in a clear “self-documenting” way.
6. **Idiomatic use of the language.** In TypeScript, make sure the typings are specific and correct. In ES2015, make sure to use imports rather than require and const instead of var, etc. Ideally a linter enforces a lot of this, but use your common sense and follow the style of the surrounding code.
