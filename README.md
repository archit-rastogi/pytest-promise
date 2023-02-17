# pytest-promise
Fulfill Resource request as a fixture

When writing a test, we may need resources that are filled in runtime.
This plugin helps adds to pytest fixture way to add dependencies on such resources.

Requirements:
1. The resource may or may not be fullfilled (by the resource manager), is therefore a `promise`.
2. Promises are scoped, and may be reused across modules, class or not, if in function scope.
3. Test and fixture may depend on multiple promises.
4. All Dependent promises are executed at once, while fixture execution is deferred.
5. Fixture execution or the test does not start until all the dependent promises are filled by some resource manager.
6. Promise execution is an asynchronous request to a resources manager or long running thread aka future, that yields one or more resources.
7. Resources may be taken away during fixture or test execution.
8. Teardown must relinquish any resource held.
9. User must be able to inspect the resources needed by a test without running.
10. User must be able to reflect upon resources filled in by the resource manager, in runtime.
11. Publish reports on stats for resources like time to full-fill, time held before release, etc.
