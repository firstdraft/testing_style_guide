# How to write tests for student projects

## North star(s)

### *Student* Readability

 - Prefer English-like syntax that anyone could almost make sense of, e.g. Capybara methods.
 - Prefer Ruby that students will understand given the course content up until the point of that project.

### Breadcrumbs
 
## Not a priority

### Speed

Although CircleCI build queue time is a consideration.

### Copy guidelines

To produce the best output for students when using `--format documentation`, 

### Notes

 - As of now, can't use `shoulda-matchers` -- nowhere to put points metadata, and throws an exception that halts test suite when a constant is uninitialized.
