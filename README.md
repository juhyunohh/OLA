# CSLM: Code-Switching Language Model Benchmark

CSLM is a benchmark designed to evaluate whether models can correctly infer and respond in the expected output language under Korean--English (KO--EN) code-switching, without explicit specification.

## Dataset Structure

CSLM consists of two settings: **Simple** and **Complex**.

### Simple Setting

The Simple setting focuses on intra-sentential code-switching, where the expected response language is the *matrix language*—the language providing the core grammatical structure into which elements from another language are embedded.

Located in `simple/`:
- **EN_Matrix_KO_Content.csv**: English matrix language with Korean embedded content 
- **KO_Matrix_EN_Content.csv**: Korean matrix language with English embedded content 

Each file contains three columns:
- `query`: The code-switched prompt
- `source`: Source identifier
- `expected_lang`: Expected response language (always "Matrix" for Simple setting)

### Complex Setting

The Complex setting involves inter-sentential code-switching, where instruction and content languages differ, and the correct response language must be inferred from task semantics.

Located in `complex/`:
- **EN_Instruction_KO_Content.csv**: English instruction with Korean content 
- **KO_Instruction_EN_Content.csv**: Korean instruction with English content 
Each file contains four columns:
- `InstrFirst`: Instruction-first query
- `ContentFirst`: Content-first query
- `source`: Source identifier (always "WildChat_1M" for Complex setting)
- `expected_lang`: Expected response language
