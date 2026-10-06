# Dotnet AI Lab

Open-source reference architecture for building AI applications and agents with **.NET, Azure and Microsoft Foundry**.

The goal of this project is to learn in public: each version adds one real capability, documents the decisions behind it (including what did not work) and ships code anyone can clone and run.

> **Status:** early stage (v0.1). The roadmap below describes what is planned, not what exists today. Check the releases and issues for the current state.

---

## What problem does this solve?

Most AI demos stop at "call a model and print the answer". Real applications also need configuration, error handling, resiliency, testing, observability and clear boundaries between domain logic and infrastructure.

Dotnet AI Lab shows how to build those pieces with the .NET ecosystem, step by step, so you can understand the trade-offs and reuse the patterns in your own projects.

## Architecture

```text
User
  ↓
ASP.NET Core API
  ↓
Application layer (orchestration)
  ↓
AI services (Microsoft Foundry / Azure)
  ↓
Response
```

Design principles:

- **Separation of concerns:** domain and application logic do not depend on a specific model provider.
- **Reproducibility:** every demo can be run locally following this README.
- **Honesty:** limitations and known issues are documented, not hidden.

Detailed notes live in [`docs/architecture`](docs/architecture) and the reasoning behind key choices in [`docs/decisions`](docs/decisions).

## Roadmap

| Version | Capability | Status |
|---------|------------|--------|
| v0.1 | Minimal .NET application | In progress |
| v0.2 | Integration with AI models | Planned |
| v0.3 | Response streaming | Planned |
| v0.4 | Configuration, resiliency and error handling | Planned |
| v0.5 | Structured outputs | Planned |
| v0.6 | RAG | Planned |
| v0.7 | Evaluation | Planned |
| v0.8 | Agents and tools | Planned |
| v0.9 | Observability | Planned |
| v1.0 | Production-oriented architecture | Planned |

Follow progress in the [issues](../../issues).

## Requirements

- [.NET SDK](https://dotnet.microsoft.com/download) (latest stable version)
- An Azure subscription (needed from v0.2 onwards)
- Access to a model deployment in Microsoft Foundry (needed from v0.2 onwards)
- Git

## Getting started

```bash
git clone https://github.com/<your-user>/DotnetAILab.git
cd DotnetAILab
dotnet build
dotnet run --project src/<ProjectName>
```

> Replace `<your-user>` and `<ProjectName>` with your own values.

## Configuration

Never commit secrets. Use user secrets or environment variables for local development:

```bash
dotnet user-secrets init --project src/<ProjectName>
dotnet user-secrets set "AI:Endpoint" "<your-endpoint>" --project src/<ProjectName>
```

Configuration keys will be documented here as each version introduces them.

## Repository structure

```text
DotnetAILab/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SECURITY.md
├── docs/
│   ├── architecture/
│   ├── tutorials/
│   └── decisions/
├── src/
├── tests/
├── samples/
├── infra/
└── presentations/
```

## Tutorials and articles

Each version is accompanied by an article explaining the problem, the decisions and what went wrong. Links will be added here as they are published.

## Contributing

Contributions, questions and feedback are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request, and use the issue templates for bugs and feature requests.

Good first contributions: improving documentation, reproducing bugs, adding tests.

## Security

If you find a security issue, please follow the instructions in [SECURITY.md](SECURITY.md) instead of opening a public issue.

## License

See [LICENSE](LICENSE).

## About the author

I'm Rodrigo, a backend developer and architect with 10+ years of experience in .NET, now building AI apps and agents with Azure and Microsoft Foundry.

- LinkedIn: [@rodrigolopreto](https://www.linkedin.com/in/rodrigolopreto)
- Blog: _add your Hashnode URL_
