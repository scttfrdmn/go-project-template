# Go Project Template

Opinionated Go CLI project scaffolding with best practices built-in.

## Features

- 🚀 **Quick Setup** - Single script creates complete project structure
- 🏗️ **Standard Layout** - cmd/, internal/, pkg/, testdata/
- 🧪 **Testing Ready** - Pre-configured with coverage, race detection
- 🔍 **Linting** - staticcheck, golangci-lint, pre-commit hooks
- 🤖 **GitHub Integration** - Auto-creates repo, labels, milestones, CI
- 📦 **Cobra CLI** - Battle-tested CLI framework pre-configured
- 🔄 **CI/CD** - GitHub Actions workflow included
- 📝 **Documentation** - README template with installation/usage

## Quick Start

```bash
# Download the setup script
curl -sSL https://raw.githubusercontent.com/scttfrdmn/go-project-template/main/setup-go-project.sh -o setup-go-project.sh
chmod +x setup-go-project.sh

# Run it
./setup-go-project.sh
```

The script will prompt you for:
- Project name (e.g., `myctl`)
- GitHub owner (user/org)
- Short description
- Version (default: `v0.1.0`)
- Whether to create README (recommended)
- Whether to create GitHub Actions CI (recommended)
- Whether to create GitHub Project board
- Whether to make repo private

## What Gets Created

```
your-project/
├── cmd/
│   └── your-project/
│       └── main.go          # CLI entry point with Cobra
├── internal/                 # Private application code
├── pkg/                      # Public library code
├── testdata/                 # Test fixtures
├── .github/
│   └── workflows/
│       └── ci.yml           # GitHub Actions CI
├── .githooks/
│   └── pre-commit           # Automated checks before commit
├── .gitignore
├── .golangci.yml            # Linter configuration
├── Makefile                 # Common development tasks
├── README.md                # Project documentation
├── go.mod
└── go.sum
```

## Makefile Targets

```bash
make check          # Fast pre-commit checks (fmt, vet, lint, short tests)
make test           # Full unit tests with coverage
make integration    # Integration/e2e tests
make build          # Build binary with version injection
make install-tools  # Install staticcheck, golangci-lint
make clean          # Remove build artifacts
```

## GitHub Setup

The script automatically creates a comprehensive set of **14 labels** for issue tracking:

**Priority Labels** (4):
- `priority:critical` 🔴 - Blocking issues
- `priority:high` 🟠 - High priority
- `priority:medium` 🟡 - Medium priority
- `priority:low` 🟢 - Low priority

**Type Labels** (6):
- `type:bug` - Something isn't working
- `type:feature` - New feature or request
- `type:refactor` - Code refactoring
- `type:docs` - Documentation
- `type:test` - Testing improvements
- `type:chore` - Maintenance tasks

**Status Labels** (2):
- `status:blocked` - Blocked by another issue
- `status:needs-info` - Needs more information

**Special Labels** (2):
- `good-first-issue` - Good for newcomers
- `help-wanted` - Extra attention needed

Plus an initial **milestone** for your first version, and optionally a **GitHub Project board** for tracking work.

## CLAUDE.md - Development Guidelines

The included `CLAUDE.md` file provides comprehensive guidelines for working with Go projects:

- **Response Style** - Concise, actionable guidance
- **Go Standards** - Go 1.23+, formatting, linting requirements
- **Code Style** - Idiomatic patterns, error handling, naming conventions
- **CLI Patterns** - Cobra usage, flags vs args, exit codes
- **AWS SDK** - Best practices for aws-sdk-go-v2
- **Testing** - Coverage targets, table-driven tests, mocking strategies
- **Security** - Credential handling, input validation, crypto
- **Git & GitHub** - Conventional commits, branch naming, PR workflow

Perfect for AI pair programming with Claude or as a team style guide.

## Prerequisites

- Go 1.23+
- Git
- [GitHub CLI (`gh`)](https://cli.github.com)

## Philosophy

This template embodies these principles:

1. **Convention over Configuration** - Sensible defaults, minimal setup
2. **Quality Gates** - Pre-commit hooks prevent bad code from being committed
3. **Fast Feedback** - `make check` runs in seconds, not minutes
4. **Test-Driven** - Easy to write and run tests, coverage tracking built-in
5. **Production-Ready** - Includes logging, error handling, graceful shutdown patterns

## Customization

After running the setup script, customize to your needs:

1. **Add Commands** - Use `cobra-cli add <command>` or manually create in `cmd/`
2. **Update README** - Replace template content with project specifics
3. **Configure Linters** - Adjust `.golangci.yml` for your preferences
4. **Add Dependencies** - `go get <package>`, run `go mod tidy`
5. **Create Issues** - Use GitHub Issues for feature tracking

## Comparison with Other Templates

| Feature | This Template | `go-blueprint` | `cobra-cli` |
|---------|--------------|----------------|-------------|
| GitHub Integration | ✅ Full | ❌ None | ❌ None |
| Pre-commit Hooks | ✅ Configured | ❌ Manual | ❌ Manual |
| CI/CD | ✅ GitHub Actions | ✅ Optional | ❌ None |
| Testing Setup | ✅ Complete | ⚠️ Basic | ❌ None |
| Makefile | ✅ Rich targets | ⚠️ Basic | ❌ None |
| AI Guidelines | ✅ CLAUDE.md | ❌ None | ❌ None |

## Examples

Projects created with this template:

- [ark](https://github.com/scttfrdmn/ark) - AWS Research Kit for academic institutions
- *(Add your project here via PR!)*

## Contributing

Improvements welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/improvement`)
3. Commit your changes (`git commit -m 'feat: add improvement'`)
4. Push to the branch (`git push origin feat/improvement`)
5. Open a Pull Request

## License

Apache 2.0 - See [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Cobra](https://github.com/spf13/cobra) - Excellent CLI framework
- [staticcheck](https://staticcheck.dev) - Superior Go linter
- [golangci-lint](https://golangci-lint.run) - Fast, comprehensive linting

---

**Questions?** Open an issue or discussion on GitHub.
