# Welcome to Nexus CLI 🔐

> **Decentralized, End-to-End Encrypted File Storage Backed by GitHub**

Nexus CLI transforms your GitHub repository into a private, encrypted file vault. Store sensitive documents, backups, and confidential files with industry-standard AES-256-GCM encryption—all managed from your command line.

---

## 🌟 What Makes Nexus Special?

| Feature | Benefit |
|---------|---------|
| 🔑 **Per-File Encryption Keys** | Share individual files without exposing your entire vault |
| 💰 **Zero-Cost Storage** | Leverage GitHub's free tier (1GB+) for encrypted backups |
| 🛡️ **Client-Side Encryption** | Your files never exist in plaintext on any server |
| 🔍 **Cryptographically Transparent** | Industry-standard AES-256-GCM & PBKDF2; full source code available |
| 📱 **Cross-Platform CLI** | Linux, macOS, Windows—same tool everywhere |
| 🌐 **Stateless & Persistent Modes** | Use without creating sessions, or cache locally for speed |
| 📚 **Git-Backed Version Control** | Complete audit trail of all operations |

---

## 🚀 Quick Start

### 1. Download
```bash
# Visit the releases page and download the latest binary for your OS
https://github.com/NexusCLI/NexusCLI/releases
```

### 2. Setup Your Vault
```bash
./nexus-cli setup <github-username> ~/.ssh/id_ed25519
# Create your vault password when prompted
```

### 3. Start Using
```bash
# Interactive shell (recommended)
./nexus-cli

# Or use commands directly
./nexus-cli upload ./document.pdf documents/report.pdf
./nexus-cli download documents/report.pdf ./report.pdf
./nexus-cli ls documents
```

---

## 📖 Documentation

- **[README.md](https://github.com/NexusCLI/NexusCLI#readme)** — Complete user guide and command reference
- **[WHITEPAPER.md](https://github.com/NexusCLI/NexusCLI/wiki/WHITEPAPER.md)** — Technical architecture, cryptography, threat models
- **[Installation Guide](https://github.com/NexusCLI/NexusCLI#installation)** — Step-by-step setup instructions
- **[Security Considerations](https://github.com/NexusCLI/NexusCLI#security-considerations)** — Encryption details & best practices

---

## 💡 Use Cases

### Personal Users
- 📄 Store financial records, medical documents, tax returns
- 💾 Cloud backup of sensitive files
- 🔐 Password manager backups
- 📸 Private photo archives

### Teams & Organizations
- 📋 Shared document repository with per-file access control
- 🔑 Secrets management alternative (CI/CD integration)
- 📤 Secure inter-organizational file transfer
- 🤝 Collaborative vaults with granular sharing

### Developers
- 🛠️ Encrypted configuration files
- 🔐 API keys and credentials management
- 📦 Secure artifact storage
- 🚀 Encrypted deployment pipelines

---

## 🔐 Security at a Glance

```
┌────────────────────────────────────────────┐
│  Your Plaintext File                       │
└────────────────────────────────────────────┘
                    ↓
         [Generate Random 32-byte Key]
                    ↓
┌────────────────────────────────────────────┐
│  AES-256-GCM Encryption                    │
│  (Unique key per file)                     │
└────────────────────────────────────────────┘
                    ↓
         [Encrypt Key with Vault Password]
         [PBKDF2-SHA256 × 100,000]
                    ↓
┌────────────────────────────────────────────┐
│  Encrypted File + Encrypted Key            │
│  → Pushed to GitHub                        │
└────────────────────────────────────────────┘
```

**Result**: Files are unreadable without your vault password, even if your GitHub repository is compromised.

---

## 📊 Project Status

| Component | Status |
|-----------|--------|
| Core CLI | ✅ Stable |
| File Operations | ✅ Stable |
| Encryption | ✅ Production-Ready |
| Per-File Sharing | ✅ Stable |
| Windows Binary | ✅ Available |
| macOS Binary | 🏗️ Compile from source |
| Linux Binary | 🏗️ Compile from source |

---

## 🤝 Contributing

We welcome contributions from the community! Whether you're interested in:

- **Code**: Bug fixes, features, optimizations
- **Documentation**: Guides, examples, translations
- **Security**: Vulnerability reports (please email instead of opening issues)
- **Testing**: Cross-platform testing and edge cases

See [CONTRIBUTING.md](https://github.com/NexusCLI/NexusCLI/blob/main/CONTRIBUTING.md) for details.

---

## 🛡️ Security & Privacy

- **Zero-Knowledge Architecture**: Your vault password is never sent to us or any server
- **Open Source**: Full source code available for security audits
- **Standard Cryptography**: AES-256-GCM and PBKDF2—no proprietary algorithms
- **No Phone Home**: No telemetry, analytics, or tracking
- **Your Infrastructure**: Your files remain on GitHub, controlled by you

### Reporting Security Issues

Please **do not** open public issues for security vulnerabilities. Instead, email: [security@nexuscli.dev](mailto:security@nexuscli.dev)

---

## 📦 Tech Stack

- **Language**: Go 1.25.6+
- **Encryption**: `crypto/aes`, `golang.org/x/crypto`
- **Git Integration**: `github.com/go-git/go-git/v5`
- **CLI Framework**: `github.com/spf13/cobra`

---

## 📝 License

Nexus CLI is released under the **MIT License**. See [LICENSE](https://github.com/NexusCLI/NexusCLI/blob/main/LICENSE) for details.

---

## 💬 Community & Support

- **Discussions**: [GitHub Discussions](https://github.com/NexusCLI/NexusCLI/discussions)
- **Issues**: [Bug Reports & Feature Requests](https://github.com/NexusCLI/NexusCLI/issues)
- **Wiki**: [Documentation & Guides](https://github.com/NexusCLI/NexusCLI/wiki)

---

## 🌍 Get Involved

⭐ **Star us on GitHub** if you find Nexus CLI useful!

```bash
# Download and try Nexus CLI today
git clone https://github.com/NexusCLI/NexusCLI.git
cd NexusCLI
go build -o nexus-cli .
./nexus-cli --help
```

---

<div align="center">

**Made with ❤️ by the Nexus CLI Community**

[Releases](https://github.com/NexusCLI/NexusCLI/releases) • [Whitepaper](https://github.com/NexusCLI/NexusCLI/wiki/WHITEPAPER.md) • [Issues](https://github.com/NexusCLI/NexusCLI/issues)

</div>
