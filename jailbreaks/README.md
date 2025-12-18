# LLM Security Research

> Academic research on LLM vulnerabilities, defenses, and prompt injection

**DISCLAIMER**: This collection is for security research and defense purposes only. Understanding attack vectors is essential for building safer AI systems.

## Attack Categories

### Black-Box Attacks
| Method | Venue | Description |
|--------|-------|-------------|
| FlipAttack | ICML'25 | Semantic flipping (81% avg success) |
| PAIR | NeurIPS'24 | Jailbreaking in 20 queries |
| TAP | NeurIPS'24 | Tree of Attacks automation |
| GASP | - | Efficient adversarial suffix generation |

### White-Box Attacks
| Method | Venue | Description |
|--------|-------|-------------|
| GCG | - | Gradient-based adversarial suffixes |
| I-GCG | ICLR'25 | Improved optimization-based |
| COLD-Attack | ICML'24 | Stealthy, controllable optimization |
| AttnGCG | - | Attention manipulation |

### Multi-Turn Attacks
| Method | Venue | Description |
|--------|-------|-------------|
| DeepInception | EMNLP'24 | Hypnotizing via role-play |
| DRA | - | Disguise and reconstruction |

### Specialized Attacks
- **Code-based**: CodeAttack, SQL Injection Jailbreak
- **Cipher-based**: SelfCipher, JAM
- **Multilingual**: Cross-language exploitation
- **ASCII Art**: ArtPrompt, ToxASCII

### Attacks on Reasoning Models
| Method | Venue | Description |
|--------|-------|-------------|
| ExtendAttack | AAAI'26 | Server attacks via extended reasoning |
| OverThink | - | Slowdown via reasoning overhead |
| H-CoT | - | Hijacking chain-of-thought safety |
| BoT | - | Backdoor breaking long thought |

## Defense Mechanisms

### Self-Reminder Defense
Reduces jailbreak success from 67.21% to 19.34%.

### SmoothLLM
Character-level perturbation defense reducing attack success to <1%.

### Recommended Defenses
- Input validation and sanitization
- Output filtering with guard models
- Rate limiting on suspicious patterns
- Multi-layer content moderation
- RLHF safety alignment

## Key Resources

### Repositories
- [tldrsec/prompt-injection-defenses](https://github.com/tldrsec/prompt-injection-defenses)
- [yueliu1999/Awesome-Jailbreak-on-LLMs](https://github.com/yueliu1999/Awesome-Jailbreak-on-LLMs)
- [CyberAlbSecOP/Awesome_GPT_Super_Prompting](https://github.com/CyberAlbSecOP/Awesome_GPT_Super_Prompting)

### Key Papers
- "Don't Say No: Jailbreaking LLM by Suppressing Refusal" (ACL'25)
- "Improved techniques for optimization-based jailbreaking" (ICLR'25)
- "DAN: Characterizing in-the-wild jailbreak prompts"

## OWASP Top 10 for LLM (2025)

**#1 Risk**: Prompt Injection

Recognized as the primary threat vector for LLM applications.
