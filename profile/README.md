<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/vaultum/.github/main/profile/logo.png">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/vaultum/.github/main/profile/logo.png">
    <img src="https://raw.githubusercontent.com/vaultum/.github/main/profile/logo.png" alt="Vaultum" width="140" height="140">
  </picture>
  
  # Vaultum
  
  ### The Operating Vault for Active Web3 Teams
  
  [![Website](https://img.shields.io/badge/website-vaultum.app-blue?style=flat-square)](https://vaultum.app)
  [![Twitter](https://img.shields.io/twitter/follow/vaultumapp?style=flat-square&logo=x&color=black)](https://twitter.com/vaultumapp)
  [![ERC](https://img.shields.io/badge/ERC-4337-purple?style=flat-square)](https://eips.ethereum.org/EIPS/eip-4337)
</div>

---

## What's the problem?

Your treasury sits in a cold storage multisig. Good. That's exactly where it should be - locked away, rarely touched, maximum security.

But here's the thing: you also have capital that needs to actually *move*. The funds your team uses every day - trades, payroll, protocol interactions. And right now, you're probably either:

1. Giving people more access than they need, or
2. Creating painful approval bottlenecks for every small transaction

Neither is great.

## What we built

Vaultum is an **Operating Vault** - a smart account designed for capital that needs to be used, not just stored.

| Your Treasury Multisig | Vaultum |
|------------------------|---------|
| The bank vault | The operating account |
| $100M locked away | $1M you actually use |
| Touched quarterly | Used daily |
| Just needs locks | Needs locks *and* rules |

We're not trying to replace your treasury. We're the second wallet you need - the one with guardrails.

---

## How it works

Open the Vaultum app, connect your hardware wallet, and set up your operating vault in minutes. No code required.

**Set spending limits** - Cap daily transactions at $5K. Even if a key gets compromised, attackers can only drain today's allowance.

**Create session keys** - Give your developer a temporary key from the dashboard. Set the expiry, spending cap, and which contracts they can call. Revoke it anytime.

**Configure allowlists** - Pick which protocols this vault can interact with. Uniswap, Aave, your own contracts. Everything else gets blocked.

**Add guardians** - Set up social recovery so you never lose access. Your guardians can recover the wallet after a configurable timelock.

**Manage your team** - Different roles get different permissions. Your treasury lead sees everything. Your junior dev gets scoped access.

All of this runs on ERC-4337, so you get gas sponsorship and batched transactions out of the box.

---

## For developers

Need programmatic access? We provide a TypeScript SDK for customers who want to integrate Vaultum into their own applications or automation workflows.

```typescript
import { VaultumClient } from '@vaultum/sdk';

const client = new VaultumClient({ chain: 'base' });

const vault = await client.createVault({
  owners: ['0xYourHardwareWallet'],
  threshold: 1,
  features: {
    spendingLimits: { daily: '5000' },
    sessionKeys: true
  }
});
```

Contact us at **dev@vaultum.app** for SDK access.

---

## Security

All Vaultum contracts and features are developed and audited by our internal security team. We don't accept external code contributions - this lets us maintain audit integrity and ship with confidence.

Found a vulnerability? Email **security@vaultum.app**.

---

## Links

[Website](https://vaultum.app) | [Docs](https://docs.vaultum.app) | [Twitter](https://twitter.com/vaultumapp)

---

<div align="center">
  <sub>Keep your treasury locked. Run your operations through Vaultum.</sub>
</div>
