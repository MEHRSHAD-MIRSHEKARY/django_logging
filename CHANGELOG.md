## v1.2.1 (2024-09-19)

### 🐛 Bug Fixes
- **fix(handlers)**: Use `localtime()` to respect `TIME_ZONE` setting. ([80322cf](https://github.com/lazarus-org/django_logging/commit/80322cf))
  - Replaced `timezone.now()` with `timezone.localtime()` in `EmailHandler` to ensure the correct local time is used for log emails, matching the configured `TIME_ZONE` setting.

### 📚 Documentation
- **docs(handlers)**: Add detailed docstrings to `EmailHandler` class and methods. ([4dc7db1](https://github.com/lazarus-org/django_logging/commit/4dc7db1))
  - Added comprehensive docstrings to the `EmailHandler` class and its methods (`emit` and `render_template`) to improve code documentation and readability.

### ✅ Tests
- **tests(settings)**: Update test settings to include `TIME_ZONE` configuration. ([94bc68a](https://github.com/lazarus-org/django_logging/commit/94bc68a))
  - Updated test settings to include `TIME_ZONE` related configurations to ensure the correct behavior when `timezone.localtime()` is used in `EmailHandler`.

### ⚡️ Miscellaneous
- **Update(SECURITY)**: Fix typo in Markdown file. ([23a9260](https://github.com/lazarus-org/django_logging/commit/23a9260))
  - Minor typo correction in the security documentation.

### 🔀 Merged
- **Merge PR #89**: Merged pull request `fix/email-timestamp`. ([2cbeb3b](https://github.com/lazarus-org/django_logging/commit/2cbeb3b))
  - Fixes an issue with incorrect timestamps in log emails by ensuring the timestamp respects the configured `TIME_ZONE` setting.

## v1.2.0 (2024-09-18)

### ✨ Features
- **refactor(templates)**: Update email template with new design and improved styles. ([a0902b7](https://github.com/lazarus-org/django_logging/commit/a0902b7))
  - Refactored the email template for log notifications to introduce a new design.
  - Updated styles with a darker background and a lighter content area.
  - Added branding with logo (LAZARUS), improved structure and readability, and modernized the look with rounded corners and shadows.

### ⚡ Refactor
- **refactor(handlers)**: Update template context data to include formatted date and time. ([55f1ded](https://github.com/lazarus-org/django_logging/commit/55f1ded))
  - Added formatted date (`%d %B %Y`) and time (`%I:%M %p`) to email context.
  - Ensured backward compatibility with existing log entries.

### ✅ Tests
- **tests(email_handler)**: Update tests to return context in `test_email_handler`. ([6e3e8cf](https://github.com/lazarus-org/django_logging/commit/6e3e8cf))
  - Modified test cases for email handling to return the context for verification.

### 📝 Documentation
- **docs**: Update LICENSE file. ([d3c00dd](https://github.com/lazarus-org/django_logging/commit/d3c00dd))

### 🔀 Merged
- **Merge PR #87**: Merged `develop` branch into `main`. ([610ecbd](https://github.com/lazarus-org/django_logging/commit/610ecbd))
- **Merge PR #86**: Merged `refactor/email-template` branch into `develop`. ([b170f99](https://github.com/lazarus-org/django_logging/commit/b170f99))

## v1.1.0 (2024-09-12)

### 🔧 Chore
- **chore(pyproject)**: Added new markers to pytest configurations. ([3a1448c](https://github.com/lazarus-org/django_logging/commit/3a1448c))
  - Updated pytest configuration with new markers for improved testing control.

### 📚 Documentation
- **docs(Usage)**: Add documentation for `execution_tracker` decorator. ([2713377](https://github.com/lazarus-org/django_logging/commit/2713377))
  - Added detailed usage instructions for the new `execution_tracker` decorator.
  - Provided examples and log output descriptions for different configurations.

- **README**: Update documentation for `execution_tracker`. ([9272093](https://github.com/lazarus-org/django_logging/commit/9272093))
  - Expanded README with detailed explanations of the `execution_tracker` decorator, including argument descriptions and usage examples.

### ✨ Features
- **feat(decorators)**: Add `execution_tracker` for performance metrics. ([3650c32](https://github.com/lazarus-org/django_logging/commit/3650c32))
  - Added a decorator that logs execution time, database queries, and query thresholds for performance monitoring.
  - Includes error handling and warnings when query thresholds are exceeded.

- **feat(validators)**: Add `integer_setting` validator in `config_validators`. ([890b2c1](https://github.com/lazarus-org/django_logging/commit/890b2c1))
  - Introduced a validator to ensure positive integer settings, improving configuration validation in `execution_tracker`.

### ✅ Tests
- **tests(decorators)**: Add tests for `execution_tracker` decorator. ([d6d3d8b](https://github.com/lazarus-org/django_logging/commit/d6d3d8b))
  - Comprehensive test coverage for the `execution_tracker` decorator, including performance, query logging, and error handling scenarios.

### ⚡ Refactor
- **docs**: Improve RST docs readability and highlights. ([6b6c12a](https://github.com/lazarus-org/django_logging/commit/6b6c12a))
  - Enhanced readability and formatting in reStructuredText documentation files for better user guidance.

### 🔀 Merged
- **Merge PR #83**: Merged `chore/pytest` into main. ([e3b3beb](https://github.com/lazarus-org/django_logging/commit/e3b3beb))
- **Merge PR #82**: Merged `update/docs` into main. ([8647a37](https://github.com/lazarus-org/django_logging/8647a37))
- **Merge PR #81**: Merged `feat/execution-tracker` into main. ([76b5621](https://github.com/lazarus-org/django_logging/commit/76b5621))

## v1.0.4 (2024-09-05)

### 🚀 CI
- **ci**: Added automated build and release process. ([1a3bb2b](https://github.com/lazarus-org/django_logging/commit/1a3bb2b))
  - Added a GitHub Actions workflow for automated build and release.
  - Workflow triggers on new tags matching the `v*.*.*` pattern.
  - Includes steps to set up Python, install dependencies, and build the package using Poetry.
  - Automatically publishes the built package to PyPI using stored PyPI token secrets.
  - Ensures the release job only runs after the 'test' job passes successfully.

### ⚡️🔨📚 Refactor
- **docs**: Updated badges in README MarkDown file. ([c82f452](https://github.com/lazarus-org/django_logging/commit/c82f452))
  - Added pylint badge to display code quality rating in `README.md`.
  - Updated pre-commit badge color.

- **docs**: Updated badges and references in RST docs. ([c82f452](https://github.com/lazarus-org/django_logging/commit/c82f452))
  - Added pylint badge to the documentation.
  - Updated the settings section in various `.rst` files to reflect recent changes.
  - Enhanced documentation for better readability and accuracy.

## v1.0.3 (2024-09-05)
### ✨ Added
- **chore(pyproject)**: Added `python-semantic-release` configuration to automate versioning and releases. (`945c648`)
- **docs**: Added pre-commit badge to display status in documentation. (`f40a9e5`, `7fca7b7`)

### 🛠️ Changed
- **docs**: Updated badge URLs and paths in documentation for correct references. (`f40a9e5`, `7fca7b7`)

### 🐛 Fixed
- **pyproject**: Updated dependencies and development requirements in the `pyproject.toml` configuration. (`945c648`)

### 🔀 Merged
- **Merge PR #77**: Merged the `chore/pyproject-config` branch into the main branch. (`c2ebad3`)

## v1.0.2 (2024-09-02)
**Added**
- tag_format in commitizen configuration in pyproject.toml
- changelog path in poetry urls
- Add FUNDING.yml file

**Refactored**
- Renamed setup_django into settings_configuration in tests dir
- Moved settings_configuration from fixtures into tests root dir


## v1.0.1 (2024-09-02)
**Refactored**
- Updated badges path in README.md and installation guide
- Updated badges path in index.rst and installation guide
- Updated headers in RestructuredText documentations

**Fixed**
- Removed repository from tool.poetry
- Fixed read the docs path in poetry urls

## v1.0.0 (2024-09-02)
- initial Release
