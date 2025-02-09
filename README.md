# Reranking Chain-of-Thought (COT) Optimization

This repository demonstrates an innovative approach to optimizing large language model (LLM) responses by extracting, reranking, and refining their internal chain-of-thought (CoT). By focusing on the most coherent and relevant parts of the CoT, we can minimize contradictory reasoning and potentially reduce token usage—ultimately leading to more reliable and efficient outputs.

## Overview

The core idea behind this project is to:
- **Extract** the internal chain-of-thought from a raw LLM response.
- **Process** the extracted reasoning by splitting it into sentences and grouping them into manageable chunks.
- **Rerank** these chunks based on relevance using a reranking model.
- **Reconstruct** a refined prompt by selecting the best segments of the chain-of-thought.
- **Generate** a final optimized response using the refined prompt.

This mechanism not only improves the clarity of the final output but also paves the way for token optimization in LLM interactions.

## Repository Contents

- [**Google Colab Notebook**](https://github.com/colesmcintosh/chain-of-though-reranking/blob/main/chain_of_thought_reranking.ipynb): An interactive version of the project that demonstrates the entire workflow in a step-by-step manner.
- **README.md**: This documentation file.

## Prerequisites

- API keys for:
  - **Cohere API** (for generating and reranking responses)
  - **Together API** (for interacting with LLM models)

## Usage

### 1. Set Up API Keys
Ensure you have your Cohere and Together API keys ready. In the provided notebook, you will be prompted to enter these keys or they can be loaded from your environment.

### 3. Run the Full Workflow
Execute the notebook cells sequentially to:
- Generate an initial raw LLM response with an embedded chain-of-thought.
- Extract and process the chain-of-thought.
- Rerank and refine the reasoning segments.
- Construct a refined prompt.
- Generate a final optimized response from the refined prompt.

### 4. Examine the Output
The final output will provide a refined answer based on the best parts of the chain-of-thought. This optimized approach aims to reduce contradictory reasoning and improve the overall quality of the response.

## How It Works

1. **Initial Response Generation**: An initial prompt is sent to an LLM, which produces a raw response containing a detailed chain-of-thought.
2. **Chain-of-Thought Extraction**: The response is parsed to extract the chain-of-thought segment.
3. **Sentence Splitting and Grouping**: The extracted CoT is split into sentences and grouped into chunks (e.g., every four sentences).
4. **Reranking**: These chunks are reranked using Cohere’s rerank model to assess their relevance to the original prompt.
5. **Prompt Reconstruction**: The top-ranked chunks are then integrated into a refined prompt.
6. **Final Response Generation**: The refined prompt is passed to another LLM model (e.g., LLaMA-3.2-3B-Instruct-Turbo) to produce a final optimized response.

## Conclusion

This project explores a novel technique to enhance LLM outputs by optimizing the internal reasoning process. By selecting the most coherent and relevant segments of the chain-of-thought, we can reduce ambiguities and potentially lower token usage. I welcome feedback and contributions from the community to further refine this methodology.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For questions, suggestions, or contributions, please open an issue or connect with me on [LinkedIn](https://www.linkedin.com/in/colemcintosh/).
