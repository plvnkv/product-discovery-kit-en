# Product repository structure

```text
my-product/
├── README.md                 # how to run the product
├── AGENTS.md                 # coding agent rules
├── docs/
│   ├── PRODUCT.md
│   ├── REQUIREMENTS.md
│   ├── DESIGN.md
│   ├── DELIVERY.md
│   ├── STATE.md
│   ├── modules/              # active modules only
│   ├── adr/                  # optional, when ADRs outgrow DESIGN
│   ├── tasks/                # optional, when tasks outgrow DELIVERY
│   ├── research/             # notes and sources without personal data
│   └── evidence/             # reports, screenshots, check results
├── app/                      # code following the chosen stack's conventions
├── tests/                    # or the stack's conventional test location
├── assets/                   # graphics, audio, licenses
└── scripts/                  # reproducible commands when needed
```

This is a logical layout, not a requirement to create empty folders. Once a stack is selected, use its standard structure: native project or engine directories may replace `app/`, for example. Document actual paths in README.

Five docs files are enough for the MVP. When moving an ADR/TASK into a separate file, leave a short index and relative link in the original document; remove duplicate text.

The working AGENTS should apply to product code. Keep the kit outside that code or in `tooling/discovery-kit/`; its AGENTS template must not accidentally become active instructions.

Do not commit secrets, real user data, or local certificates. When configuration is introduced, add `.env.example` with names and safe examples only, and configure `.gitignore` for the actual stack. Record build and check commands after running them, not based on assumptions.
