# ZipLLM Website

This website illustrates the content of the research paper "ZipLLM: Efficient LLM Storage via Model-Aware Synergistic Data Deduplication and Compression" for NSDI '26.

## Project Structure

- `index.html` - Main HTML file
- `style.css` - CSS styling
- `images/` - SVG illustrations used on the website

## Running the Website

Simply open `index.html` in a web browser to view the website.

## Paper Abstract

Modern model hubs, such as Hugging Face, store tens of petabytes of LLMs, with fine-tuned variants vastly outnumbering base models and dominating storage consumption. Existing storage reduction techniques—such as deduplication and compression—are either LLM-oblivious or not compatible with each other, limiting data reduction effectiveness.

Our large-scale characterization study across all publicly-available Hugging Face LLM repositories reveals several key insights: (1) fine-tuned models within the same family exhibit highly structured, sparse parameter differences suitable for delta compression; (2) bitwise similarity enables LLM family clustering; and (3) tensor-level deduplication offers strong synergy with model-aware compressors.

Building on these insights, we present BitX, an effective, fast, lossless delta compression algorithm that compresses XORed redundancy between fine-tuned and base LLMs. We build ZipLLM, a model storage reduction pipeline that unifies tensor-level deduplication and lossless BitX compression. By synergizing deduplication and compression around LLM family clustering, ZipLLM reduces model storage consumption by 49.5%, over 20% more than state-of-the-art deduplication and compression designs.

## Key Contributions

1. Comprehensive analysis of Hugging Face's massive-scale model repository, focusing on how LLM family structure impacts storage redundancy and compression effectiveness.
2. Introduction of bit distance, a novel metric to quantify similarity between fine-tuned models and their base models.
3. Development of BitX, a highly effective, fast, lossless delta compression algorithm.
4. Identification of a new ML system design principle: deduplication and lossless compression must be co-designed and unified.
5. Implementation of ZipLLM, a model storage reduction pipeline that synergizes tensor-level deduplication and lossless BitX compression. 