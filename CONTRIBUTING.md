# Contributing to Vaultum

First off, thank you for considering contributing to Vaultum! 🎉

We're building the future of programmable security for digital assets, and every contribution helps make Web3 safer and more accessible.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Process](#development-process)
- [Style Guides](#style-guides)
- [Community](#community)

## 📜 Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md). We're committed to providing a welcoming and inclusive environment for all contributors.

## 🤝 How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates.

**When reporting bugs, include:**
- Clear, descriptive title
- Steps to reproduce
- Expected vs actual behavior
- Environment details (OS, versions)
- Screenshots/videos if applicable
- Code samples or test cases

### 💡 Suggesting Features

We love new ideas! When suggesting features:
- Check if it's already suggested
- Provide clear use cases
- Explain why it benefits users
- Consider implementation complexity
- Include mockups/diagrams if relevant

### 🔧 Pull Requests

#### For First-Time Contributors

1. Fork the repository
2. Create your feature branch
3. Make your changes
4. Test thoroughly
5. Submit a PR

#### PR Guidelines

- **One feature per PR** - Keep PRs focused
- **Write tests** - Maintain or improve coverage
- **Update docs** - Include relevant documentation
- **Follow style** - Match existing code style
- **Clear commits** - Write meaningful commit messages
- **Link issues** - Reference related issues

### 📖 Improving Documentation

Documentation is crucial! You can help by:
- Fixing typos and grammar
- Improving clarity
- Adding examples
- Translating docs
- Creating tutorials

## 🔄 Development Process

### 1. Setting Up Your Environment

#### Smart Contracts (Solidity)
```bash
git clone https://github.com/vaultum/contracts
cd contracts
forge install
forge test
```

#### JavaScript SDK
```bash
git clone https://github.com/vaultum/sdk-js
cd sdk-js
pnpm install
pnpm test
```

#### PHP SDK
```bash
git clone https://github.com/vaultum/sdk-php
cd sdk-php
composer install
composer test
```

### 2. Making Changes

1. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/issue-description
   ```

2. **Make your changes**
   - Write clean, readable code
   - Add tests for new features
   - Update documentation

3. **Test your changes**
   ```bash
   # Run tests specific to the repo
   forge test         # Contracts
   pnpm test         # JS SDK
   composer test     # PHP SDK
   ```

4. **Commit your changes**
   ```bash
   git commit -m "feat: add session key rotation"
   # or
   git commit -m "fix: resolve gas estimation issue"
   ```

### 3. Submitting Your PR

1. Push to your fork
2. Open a PR against `main`
3. Fill out the PR template
4. Wait for review
5. Address feedback
6. Celebrate when merged! 🎉

## 🎨 Style Guides

### Git Commit Messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `style:` - Code style changes
- `refactor:` - Code refactoring
- `test:` - Test additions/changes
- `chore:` - Maintenance tasks

Examples:
```
feat: add spending limit reset function
fix: correct session key expiry validation
docs: update SDK installation guide
```

### Solidity Style Guide

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

/**
 * @title ContractName
 * @notice Brief description
 * @dev Implementation details
 */
contract ContractName {
    // State variables
    uint256 private constant MAX_VALUE = 100;
    mapping(address => uint256) private balances;
    
    // Events
    event ValueChanged(address indexed user, uint256 newValue);
    
    // Modifiers
    modifier onlyOwner() {
        require(msg.sender == owner, "Not owner");
        _;
    }
    
    // Functions (external, public, internal, private)
    function setValue(uint256 _value) external onlyOwner {
        require(_value <= MAX_VALUE, "Exceeds max");
        // Implementation
    }
}
```

### JavaScript/TypeScript Style

```typescript
/**
 * Creates a new smart account
 * @param owner - The account owner address
 * @param modules - Security modules to enable
 * @returns The created account details
 */
export async function createAccount(
  owner: Address,
  modules: Module[] = []
): Promise<Account> {
  // Implementation
}
```

### PHP Style

```php
<?php

namespace Vaultum\SDK;

/**
 * Manages user operations
 */
class OperationManager
{
    /**
     * Submit a user operation
     * 
     * @param UserOperation $operation The operation to submit
     * @return string The operation hash
     * @throws ValidationException If operation is invalid
     */
    public function submit(UserOperation $operation): string
    {
        // Implementation
    }
}
```

## 🧪 Testing Guidelines

### Test Coverage Requirements

- Smart Contracts: 95%+ coverage
- SDKs: 80%+ coverage
- Critical paths: 100% coverage

### Writing Tests

#### Solidity Tests
```solidity
function test_SessionKeyExpiry() public {
    vm.warp(block.timestamp + 1 days);
    vm.expectRevert("Session expired");
    account.executeWithSessionKey(op);
}
```

#### JavaScript Tests
```javascript
describe('SessionKey', () => {
  it('should expire after timeout', async () => {
    const key = await createSessionKey({ expiry: 3600 });
    await time.increase(3601);
    await expect(key.execute(op)).to.be.rejected;
  });
});
```

## 🚀 Release Process

1. **Version Bump** - Update version numbers
2. **Changelog** - Update CHANGELOG.md
3. **Testing** - Run full test suite
4. **Review** - Code review by maintainers
5. **Release** - Tag and publish

## 📚 Learning Resources

New to Vaultum or Web3 development?

- [ERC-4337 Explained](https://docs.vaultum.app/concepts/account-abstraction)
- [Vaultum Architecture](https://docs.vaultum.app/architecture)
- [Smart Contract Best Practices](https://docs.vaultum.app/security)
- [Video Tutorials](https://youtube.com/@vaultum) (coming soon)

## 🏆 Recognition

We value all contributions! Contributors are recognized through:

- Credits in release notes
- Contributors page on website
- Special Discord role
- Vaultum NFT badges (coming soon)

## ❓ Questions?

- **Discord**: [Join our server](https://discord.gg/vaultum)
- **GitHub Discussions**: [Ask here](https://github.com/orgs/vaultum/discussions)
- **Twitter/X**: [@vaultumapp](https://twitter.com/vaultumapp)

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for making Vaultum better! 💙

*"Your keys. Your rules. Our community."*
