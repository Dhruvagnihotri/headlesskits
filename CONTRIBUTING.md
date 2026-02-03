# Contributing to HeadlessKit

Thank you for your interest in contributing to HeadlessKit! 🎉

## Ways to Contribute

- 🐛 **Report bugs** - Found a bug? Open an issue
- 💡 **Suggest features** - Have an idea? Start a discussion
- 📖 **Improve documentation** - Docs can always be better
- 🔧 **Submit code** - Fix bugs or add features
- 💬 **Help others** - Answer questions in discussions
- ⭐ **Spread the word** - Star, share, and tell others

## Getting Started

### 1. Fork the Repository

HeadlessKit is a collection of repositories. Choose the one you want to contribute to:

- [react-headless-auth](https://github.com/Dhruvagnihotri/react-headless-auth) - React authentication
- [flask-headless-auth](https://github.com/Dhruvagnihotri/flask-headless-auth) - Flask authentication
- [react-headless-payments](https://github.com/Dhruvagnihotri/react-headless-payments) - React payments
- [flask-headless-payments](https://github.com/Dhruvagnihotri/flask-headless-payments) - Flask payments
- [headlesskits](https://github.com/Dhruvagnihotri/headlesskits) - Documentation hub

### 2. Set Up Development Environment

**For React packages:**
```bash
git clone https://github.com/YOUR_USERNAME/react-headless-auth.git
cd react-headless-auth
npm install
npm run dev
```

**For Flask packages:**
```bash
git clone https://github.com/YOUR_USERNAME/flask-headless-auth.git
cd flask-headless-auth
pip install -e ".[dev]"
pytest
```

### 3. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-description
```

### 4. Make Your Changes

- Write clear, readable code
- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Keep commits atomic and well-described

### 5. Test Your Changes

**React:**
```bash
npm test
npm run lint
npm run type-check
```

**Flask:**
```bash
pytest
flake8
mypy .
```

### 6. Submit a Pull Request

1. Push your branch to your fork
2. Open a PR against the main repository
3. Fill out the PR template
4. Wait for review

## Code Style

### Python (Flask packages)

- Follow [PEP 8](https://pep8.org/)
- Use type hints
- Write docstrings for public functions
- Keep functions small and focused
- Maximum line length: 100 characters

```python
def process_payment(
    amount: int,
    currency: str = "USD",
    metadata: Optional[Dict[str, Any]] = None
) -> Payment:
    """
    Process a payment transaction.
    
    Args:
        amount: Payment amount in cents
        currency: ISO currency code
        metadata: Optional payment metadata
        
    Returns:
        Payment object with transaction details
        
    Raises:
        PaymentError: If payment processing fails
    """
    # Implementation
```

### TypeScript/React

- Use TypeScript for all new code
- Follow React best practices
- Use functional components and hooks
- Keep components small and focused
- Maximum line length: 100 characters

```typescript
interface PaymentFormProps {
  amount: number;
  onSuccess?: (payment: Payment) => void;
  onError?: (error: Error) => void;
}

export const PaymentForm: React.FC<PaymentFormProps> = ({
  amount,
  onSuccess,
  onError,
}) => {
  // Implementation
};
```

## Commit Messages

Use clear, descriptive commit messages:

```
feat: add OAuth support for GitHub
fix: resolve token refresh race condition
docs: update authentication guide
test: add tests for payment processing
refactor: simplify error handling
```

Prefixes:
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation only
- `test:` - Adding or updating tests
- `refactor:` - Code refactoring
- `perf:` - Performance improvement
- `chore:` - Maintenance tasks

## Pull Request Guidelines

### PR Title Format

```
[Package] Type: Brief description

Examples:
[React Auth] feat: add biometric authentication support
[Flask Payments] fix: handle webhook retry logic
[Docs] docs: add Vue.js integration guide
```

### PR Description Template

```markdown
## Description
Brief description of what this PR does

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
- [ ] Tests pass locally
- [ ] Added new tests for new features
- [ ] Manual testing completed

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] No new warnings
```

## Reporting Bugs

### Before Reporting

1. Check if the bug is already reported
2. Try the latest version
3. Gather relevant information

### Bug Report Template

```markdown
**Describe the bug**
Clear description of the bug

**To Reproduce**
Steps to reproduce:
1. Go to '...'
2. Click on '....'
3. See error

**Expected behavior**
What should happen

**Actual behavior**
What actually happens

**Environment:**
- Package: [e.g., react-headless-auth@1.0.0]
- OS: [e.g., macOS 13.0]
- Browser: [e.g., Chrome 120]
- Framework: [e.g., React 18.2.0]

**Additional context**
Logs, screenshots, etc.
```

## Feature Requests

Start a [discussion](https://github.com/Dhruvagnihotri/headlesskits/discussions) with:

1. **Problem**: What problem does this solve?
2. **Solution**: Your proposed solution
3. **Alternatives**: Other options you considered
4. **Additional context**: Any other relevant information

## Documentation

Documentation improvements are always welcome!

- Fix typos
- Clarify unclear sections
- Add examples
- Improve code samples
- Translate to other languages

## Community Guidelines

- Be respectful and inclusive
- Help others learn and grow
- Give constructive feedback
- Follow the [Code of Conduct](./CODE_OF_CONDUCT.md)

## Recognition

Contributors will be:
- Listed in the project's contributors page
- Mentioned in release notes (for significant contributions)
- Eligible for special contributor badges

## Questions?

- 💬 [Start a discussion](https://github.com/Dhruvagnihotri/headlesskits/discussions)
- 📧 [Email us](mailto:dagni@umich.edu)

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to HeadlessKit! 🙏
