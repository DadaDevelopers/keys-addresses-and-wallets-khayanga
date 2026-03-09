# Assignment 2

## Generate legacy addresses, bech32 addresses and bech32m addresses

### 1. Generate a Legacy Address

Command:

```bash
./build/bin/bitcoin-cli -regtest getnewaddress "" legacy
```

Output:

```
miBUAWrzzwgKLbcCgEXNBnpMkZY6reM2Pa
```

Legacy addresses are the original Bitcoin address format.

---

### 2. Generate a Bech32 Address (SegWit)

Command:

```bash
./build/bin/bitcoin-cli -regtest getnewaddress "" bech32
```

Output:

```
bcrt1qq09a4w9g2l6rkgh5629gvzarlgdrrhl5ekvtuw
```

Bech32 addresses are used for **SegWit transactions** and offer lower transaction fees and better error detection.

---

### 3. Generate a Bech32m Address (Taproot)

Command:

```bash
./build/bin/bitcoin-cli -regtest getnewaddress "" bech32m
```

Output:

```
bcrt1pafugfpvn220wd0dl7dezceh9mzjwxlcytug4enw44mjlyxf8u0kqtf32uu
```

Bech32m addresses are used for **Taproot**, which improves privacy, efficiency, and smart contract functionality in Bitcoin.

---

# Difference Between Hardened and Non-Hardened Keys

## Hardened Keys

Hardened keys are derived using the **parent private key**, which means child keys cannot be derived from the parent public key.

Characteristics:

- Requires the parent private key
- Provides stronger security
- Prevents certain types of key compromise attacks

---

## Non-Hardened Keys

Non-hardened keys can be derived from the **parent public key**.

Characteristics:

- Allows generating child public keys without exposing the private key
- Useful for watch-only wallets
- Slightly less secure compared to hardened keys

---

# Why Wallet Developers Prefer Deterministic Wallets

Deterministic wallets generate all keys from a **single seed phrase**.

Advantages:

### Easier Backup
Users only need to back up **one seed phrase** instead of multiple private keys.

### Predictable Key Generation
All addresses are derived from the same seed, meaning the wallet can always regenerate them.

### Better Wallet Management
Developers can organize wallets using hierarchical structures such as **HD wallets (BIP32)**.

### Easy Recovery
If a user loses their device, the wallet can be restored using the **seed phrase**.

---

# Conclusion

In this assignment I:

- Generated **Legacy addresses**
- Generated **Bech32 (SegWit) addresses**
- Generated **Bech32m (Taproot) addresses**
- Explained the difference between **hardened and non-hardened keys**
- Explained why developers prefer **deterministic wallets**
