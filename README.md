# pytest-promise
Fulfill Resource request as a fixture

When writing a test, we may need resources that are filled in runtime.
This plugin helps adds to pytest fixture way to add dependencies on such resources.

Requirements:
1. The resource may or may not be fullfilled (by the resource manager).
2. Resource are scoped, and may be reused across modules, class or not, if in function scope.
3. Test and fixture may depend on multiple resources.
4. All Dependent resources are required for test execution.
5. Fixture execution or the test does not start until all the resources are filled by some resource manager.
6. Fixture may execute eagerly if resources are filled.
7. Resources may be taken away during fixture or test execution.
8. Teardown must relinquish any resource held.
9. User must be able to inspect resources needed by a test without running.
10. User must be able to reflect upon resources filled in by the resource manager, in runtime.
11. Publish reports on stats for resources like time to full-fill, time held before release, etc.
