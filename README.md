# CSLM: Code-Switching Language Model Benchmark

CSLM is a benchmark designed to evaluate whether models can correctly infer and respond in the expected output language under Korean--English (KO--EN) code-switching, without explicit specification.

## Dataset Structure

CSLM consists of two settings: **Simple** and **Complex**.

### Simple Setting

The Simple setting focuses on intra-sentential code-switching, where the expected response language is the *matrix language*—the language providing the core grammatical structure into which elements from another language are embedded.

Located in `simple/`:
- **EN_Matrix_KO_Content.csv**: English matrix language with Korean embedded content (258 examples)
- **KO_Matrix_EN_Content.csv**: Korean matrix language with English embedded content (283 examples)

Each file contains two columns:
- `codeswitch`: The code-switched prompt
- `source`: Source identifier

### Complex Setting

The Complex setting involves inter-sentential code-switching, where instruction and content languages differ, and the correct response language must be inferred from task semantics.

Located in `complex/`:
- **EN_Instruction_KO_Content.csv**: English instruction with Korean content (272 examples)
- **KO_Instruction_EN_Content.csv**: Korean instruction with English content (58 examples)

Each file contains three columns:
- `InstrFirst`: Instruction-first format
- `ContentFirst`: Content-first format
- `expected_lang`: Expected response language

## Data Sources

- **Simple Setting**: Initial prompts collected from the monolingual Language Confusion Benchmark (199 EN) and WildChat 1M (100 KO)
- **Complex Setting**: Based on qualitative analysis of 3K code-switching utterances from LLM–user interactions. 60 representative instruction templates (30 per category) from WildChat 1M, with four content variations per template.

## Citation

If you use this dataset, please cite:

```bibtex
@article{cslm2024,
  title={CSLM: Code-Switching Language Model Benchmark},
  author={...},
  year={2024}
}
```

