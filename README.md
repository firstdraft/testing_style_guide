# How to write tests for student projects

## North star(s)

### *Student* Readability

 - Prefer English-like syntax that anyone could almost make sense of, e.g. Capybara methods.
 - Prefer Ruby that students will understand given the course content up until the point of that project.

### Breadcrumbs

 - Break tasks up into tiny little steps
 - Each test should act as a breadcrumb leading to a solution; but avoid constraining implementation
 - It's more refinements of functionality as opposed to steps towards implementation, e.g.
   1. There's a form on the page
   1. The form has an input
   1. The input has a label
   1. There's a submit button
   1. The submit button, when clicked, takes you to the correct next page
   1. The submit button, when clicked, does the right CRUD thing
 - These are all things that need to happen, but we test them in a particular order that will help students if they get stuck (this is why we disable rspec's default behavior of randomizing test order)

## Not a priority

### Speed

Although CircleCI build queue time is a consideration.

### Copy guidelines

To produce the best output for students when using `--format documentation`,

### Notes

 - As of now, can't use `shoulda-matchers` -- nowhere to put points metadata, and throws an exception that halts test suite when a constant is uninitialized.


 - For filling in form inputs, select using label copy, not attributes
  - How flexible is `fill_in` in terms of case insensitivity, stripping whitespace, etc.
 - Don't use `before` or `let`; every test must be self-contained. I.e. avoid "Mystery Guests": https://robots.thoughtbot.com/mystery-guest
 - Some tests pass out of the box; but right now, the weights of points are off/meaningless, because you start out with like 65% of the points already. Analyze this and fix.
  - For one thing, right now the tests are just bad/brittle. For example, in Omnicalc, the test for mode is so stupid. Because the value is already on the page, because it's in the list of numbers. We need to check for its presence within some particular CSS instead (even though we want to avoid having opinions about implementation details like CSS classes, in some cases there might not be a choice).
 - Be smart/flexible about rounding, or be very explicit in the specs about what to do.
 - Goal: add a hint for every single test.
 - Is FactoryGirl worth it? We can include the syntax so that we can omit `FactoryGirl.` and just say `create`.
 - These should be fully tested applications; but we just decide which of the tests we want to assign points based on what we're learning in this project. (But maybe put irrelevant tests in their own separate files.)
 - It's fair to specify copy and URLs in tests. Students should be allowed to make all other implementation choices. CSS selectors should not be used in tests to find elements unless explicitly testing CSS.
 - Use good copy in tests, e.g., "alice@example.com" and "bob@example.com" rather than "1" and "2" (just as we avoid x and y as variable names).


- Think about:
  - Require PRs and links to code for all questions
  - automatically setting up CircleCI
  - Whatever happened to Percy
  - First Draft Grades can be a CI status on a PR  
  - Review Apps
  - Private repos
