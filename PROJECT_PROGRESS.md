# Project progress

## Completed parts

- Part 0: Read all 26 pages of the Version 2.0 subject, inspect the supplied
  archives, and verify the implementation plan against the subject.
- Part 1: Set up uv, the Python package, development checks, and Makefile.
  All setup checks passed on Python 3.12.3.

## Current part

- Part 1 implementation and verification complete; learning checkpoint pending.
- Stop after this part for the learner's questions and explicit approval.

## Pending parts

2. Required Pydantic models and validation.
3. Corpus discovery and loading.
4. Python chunking.
5. Markdown/text chunking.
6. Index construction and persistence.
7. Lexical retrieval with BM25 or TF-IDF.
8. Single-query and batch search.
9. Local Qwen/Qwen3-0.6B integration.
10. Context preparation and grounded answer generation.
11. Complete Python Fire CLI and JSON outputs.
12. Recall evaluation, performance measurement, and optimization.
13. Robustness and integration checks.
14. README, final integration, and defense preparation.

## Created files and their purpose

- `pyproject.toml`: project metadata and development dependencies.
- `uv.lock`: generated reproducible dependency resolution.
- `Makefile`: install, run, debug, clean, and lint commands.
- `.gitignore`: exclude local data, environments, caches, and model artifacts.
- `.flake8`: exclude dependencies and corpus/model directories from lint discovery.
- `src/__init__.py`: package documentation.
- `src/__main__.py`: executable package entry point.
- `PROJECT_PROGRESS.md`: learning progress and verification record.

## Implemented functions

- `src.__main__.main() -> None`: print an explicit setup-status message.
  No retrieval or generation commands are implemented yet.

## Important design decisions

- Use Python >=3.10 and uv; the evaluator invokes `uv sync`.
- Keep `src` directly runnable with `uv run python -m src`.
- Add runtime dependencies when their implementation part first needs them.
- Keep corpus files, weights, generated indexes, and outputs out of Git.
- Preserve the supplied moulinette README until the documentation part.
- Default index location will be `data/processed/`; all input/output paths
  will be configurable in the completed CLI.
- Never import or call the official moulinette from the implementation.
- Development test programs are not submitted, per the subject.
- Flake8 and mypy exclude third-party environments and local corpus/model data;
  the required root-level check commands still inspect our implementation.

## Tests and checks

- Part 0: PDF extraction and reading succeeded for all 26 pages.
- Part 1: Python 3.12.3 and make are available.
- Part 1: uv is available at `/tmp/rag-part1-tools/bin/uv`, outside normal PATH.
- `make install`: passed; uv created `.venv` and installed development tools.
- `uv sync --locked`: passed; metadata and lockfile agree.
- `make run`: passed; printed the explicit setup-status message.
- First `make lint`: failed because flake8 scanned third-party `.venv` files.
  Added `.flake8` exclusions and matching mypy discovery exclusions.
- Final `make lint`: passed; flake8 reported no issues and mypy reported
  success for both source files.
- `make debug`: passed with debugger input `continue` then `quit`;
  a subprocess assertion verified that the setup message was printed.
- `make clean`: passed; a subsequent `make run` also passed.
- `git check-ignore`: confirmed environment, ZIP archives, runtime data,
  and model weights are ignored.
- `git diff --check`: passed (new files are still untracked).

## Known issues and limitations

- Only the package setup exists; all RAG functionality is pending.
- The existing README documents the moulinette, not our application.
- Source range ending-index conventions need explicit documentation and tests.
- Actual retrieval scores, timings, and local model resource needs are untested.

## Next steps

- Complete the Part 1 learning checkpoint.
- Wait for learner understanding and approval before Part 2.
