# Protenix Model Architecture Analysis Plan

## Objective
Perform a **deep-dive read-only analysis** of the Protenix model folder (`protenix/model/`) to document the complete architecture, including all classes, methods, parameters, and relationships.

## Output
- **Format**: Markdown document with Mermaid diagrams and detailed class/function hierarchy
- **Depth**: Deep dive - every class, method, parameter, and relationship
- **Location**: `C:\Users\Pau\Desktop\2026\Stanford-RNA\Documentation\`

---

## Codebase Structure (protenix/model/)

```
protenix/model/
├── __init__.py
├── protenix.py          # Main model entry point
├── generator.py         # Structure generation logic
├── loss.py              # Loss functions
├── sample_confidence.py # Confidence scoring
├── utils.py             # Model utilities
├── modules/
│   ├── confidence.py    # Confidence head modules
│   ├── diffusion.py     # Diffusion model components
│   ├── embedders.py     # Input embeddings
│   ├── frames.py        # Frame/coordinate handling
│   ├── head.py          # Output heads
│   ├── pairformer.py    # Pairformer blocks
│   ├── primitives.py    # Basic building blocks
│   └── transformer.py   # Transformer components
├── triangular/
│   ├── layers.py        # Triangular layers
│   └── triangular.py    # Triangular attention/update
├── tri_attention/
│   ├── op.py            # Triangular attention ops
│   ├── forward.py       # Forward pass
│   ├── backward.py      # Backward pass
│   └── autotune*.py     # Auto-tuning utilities
└── layer_norm/
    ├── layer_norm.py    # Custom LayerNorm
    ├── torch_ext_compile.py
    └── kernel/          # CUDA kernels
```

---

## Work Plan

### Phase 1: Core Model Analysis
- [ ] **1.1** Analyze `protenix.py` - Main model class, forward pass, component orchestration
- [ ] **1.2** Analyze `generator.py` - Structure generation and sampling logic
- [ ] **1.3** Analyze `loss.py` - All loss functions and their parameters
- [ ] **1.4** Analyze `sample_confidence.py` - Confidence metrics computation
- [ ] **1.5** Analyze `utils.py` - Utility functions and helpers

### Phase 2: Modules Deep Dive
- [ ] **2.1** Analyze `modules/primitives.py` - Base building blocks (Linear, Attention, etc.)
- [ ] **2.2** Analyze `modules/embedders.py` - Input embedding layers
- [ ] **2.3** Analyze `modules/transformer.py` - Transformer architecture
- [ ] **2.4** Analyze `modules/pairformer.py` - Pairformer blocks (key AlphaFold3-style component)
- [ ] **2.5** Analyze `modules/diffusion.py` - Diffusion model components
- [ ] **2.6** Analyze `modules/frames.py` - Frame and coordinate transformations
- [ ] **2.7** Analyze `modules/head.py` - Output prediction heads
- [ ] **2.8** Analyze `modules/confidence.py` - Confidence prediction modules

### Phase 3: Triangular Components
- [ ] **3.1** Analyze `triangular/triangular.py` - Triangular attention/multiplicative update
- [ ] **3.2** Analyze `triangular/layers.py` - Triangular layer implementations
- [ ] **3.3** Analyze `tri_attention/` - Optimized triangular attention operations

### Phase 4: Layer Norm & Low-Level
- [ ] **4.1** Analyze `layer_norm/layer_norm.py` - Custom LayerNorm implementation
- [ ] **4.2** Document CUDA kernel integration approach

### Phase 5: Documentation Generation
- [ ] **5.1** Create high-level architecture diagram (Mermaid)
- [ ] **5.2** Create detailed module interaction diagrams
- [ ] **5.3** Document class hierarchies with all methods/parameters
- [ ] **5.4** Document data flow through the model
- [ ] **5.5** Compile final markdown document
- [ ] **5.6** Save to `C:\Users\Pau\Desktop\2026\Stanford-RNA\Documentation\`

---

## Agent Strategy

### Primary Agent: `explore` (parallel)
Used for initial file analysis - can run multiple in parallel:
- Fast code exploration and question answering
- Extract class definitions, method signatures, docstrings
- Identify inheritance and composition relationships

### Secondary Agent: `general-purpose`
Used for complex synthesis tasks:
- Compile findings into coherent architecture documentation
- Generate Mermaid diagrams from analyzed relationships
- Create the final comprehensive markdown document

### Direct Tools (for verification)
- `view` - Read specific files when needed
- `grep` - Search for specific patterns (class definitions, imports, inheritance)

---

## Notes

- **Read-only analysis**: No code modifications will be made
- **Focus**: `protenix/model/` folder as specified
- **Output quality**: Deep dive with every class, method, parameter documented
- **Diagrams**: Mermaid format for GitHub/VS Code compatibility
