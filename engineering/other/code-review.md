---
description: >-
  This guide contains advice and best practices for performing code review, and
  having your code reviewed.
---

# Code Review

### Everyone

* Accept that many programming decisions are opinions. Discuss tradeoffs, which you prefer, and reach a resolution quickly.
* Ask questions; don’t make demands. \(“What do you think about naming this `:user_id`?”\)
* Ask for clarification. \(“I didn’t understand. Can you clarify?”\)
* Avoid selective ownership of code. \(“mine”, “not mine”, “yours”\)
* Avoid using terms that could be seen as referring to personal traits. \(“dumb”, “stupid”\). Assume everyone is attractive, intelligent, and well-meaning.
* Be explicit. Remember people don’t always understand your intentions online.
* Be humble. \(“I’m not sure - let’s look it up.”\)
* Don’t use hyperbole. \(“always”, “never”, “endlessly”, “nothing”\)
* Be careful about the use of sarcasm. Everything we do is public; what seems like good-natured ribbing to you and a long-time colleague might come off as mean and unwelcoming to a person new to the project.
* Consider one-on-one chats or video calls if there are too many “I didn’t understand” or “Alternative solution:” comments. Post a follow-up comment summarizing one-on-one discussion.
* If you ask a question to a specific person, always start the comment by mentioning them; this will ensure they see it if their notification level is set to “mentioned” and other people will understand they don’t have to respond.

### Having Your Code Reviewed

Please keep in mind that code review is a process that can take multiple iterations, and reviewers may spot things later that they may not have seen the first time.

* The first reviewer of your code is _you_. Before you perform that first push of your shiny new branch, read through the entire diff. Does it make sense? Did you include something unrelated to the overall purpose of the changes? Did you forget to remove any debugging code?
* Be grateful for the reviewer’s suggestions. \(“Good call. I’ll make that change.”\)
* Don’t take it personally. The review is of the code, not of you.
* Explain why the code exists. \(“It’s like that because of these reasons. Would it be more clear if I rename this class/file/method/variable?”\)
* Extract unrelated changes and refactorings into future merge requests/issues.
* Seek to understand the reviewer’s perspective.
* Try to respond to every comment.
* The merge request author resolves only the discussions they have fully addressed. If there’s an open reply, an open discussion, a suggestion, a question, or anything else, the discussion should be left to be resolved by the reviewer.
* Push commits based on earlier rounds of feedback as isolated commits to the branch. Do not squash until the branch is ready to merge. Reviewers should be able to read individual updates based on their earlier feedback.

### Reviewing Code

Understand why the change is necessary \(fixes a bug, improves the user experience, refactors the existing code\). Then:

* Communicate which ideas you feel strongly about and those you don't.
* Identify ways to simplify the code while still solving the problem.
* If discussions turn too philosophical or academic, move the discussion offline to a regular Friday afternoon technique discussion. In the meantime, let the author make the final decision on alternative implementations.
* Offer alternative implementations, but assume the author already considered them. \("What do you think about using a custom validator here?"\)
* Seek to understand the author's perspective.
* Sign off on the pull request with a 👍 or "Ready to merge" comment.
* Remember that you are here to provide feedback, not to be a gatekeeper.

### The right balance

One of the most difficult things during code review is finding the right balance in how deep the reviewer can interfere with the code created by a reviewee.

* Learning how to find the right balance takes time; that is why we have reviewers that become maintainers after some time spent on reviewing merge requests.
* Finding bugs and improving code style is important, but thinking about good design is important as well. Building abstractions and good design is what makes it possible to hide complexity and makes future changes easier.
* Asking the reviewee to change the design sometimes means the complete rewrite of the contributed code. It’s usually a good idea to ask another maintainer or reviewer before doing it, but have the courage to do it when you believe it is important.
* There is a difference in doing things right and doing things right now. Ideally, we should do the former, but in the real world we need the latter as well. A good example is a security fix which should be released as soon as possible. Asking the reviewee to do the major refactoring in the merge request that is an urgent fix should be avoided.
* Doing things well today is usually better than doing something perfectly tomorrow. Shipping a kludge today is usually worse than doing something well tomorrow. When you are not able to find the right balance, ask other people about their opinion.



Based on [https://docs.gitlab.com/ee/development/code\_review.html](https://docs.gitlab.com/ee/development/code_review.html) and [https://github.com/thoughtbot/guides/tree/master/code-review](https://github.com/thoughtbot/guides/tree/master/code-review)

