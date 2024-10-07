# Denoising with a Joint-Embedding Predictive Architecture (D-JEPA)

![Pipeline](assets/pipeline.png)

Welcome to the official repository for the paper "Denoising with a Joint-Embedding Predictive Architecture" (D-JEPA). This repository contains the implementation of the methods described in the paper.

Since the paper is currently under anonymous review, some links that might reveal author information have been hidden.

## Abstract

Joint-embedding predictive architectures (JEPAs) have shown substantial promise in self-supervised representation learning, yet their application in generative modeling remains underexplored. Conversely, diffusion models have demonstrated significant efficacy in modeling arbitrary probability distributions. In this paper, we introduce Denoising with a Joint-Embedding Predictive Architecture (D-JEPA), pioneering the integration of JEPA within generative modeling. By recognizing JEPA as a form of masked image modeling, we reinterpret it as a generalized next-token prediction strategy, facilitating data generation in an auto-regressive manner. Furthermore, we incorporate diffusion loss to model the per-token probability distribution, enabling data generation in a continuous space. We also adapt flow matching loss as an alternative to diffusion loss, thereby enhancing the flexibility of D-JEPA. Empirically, with increased GFLOPs, D-JEPA consistently achieves lower FID scores with fewer training epochs, indicating its good scalability. Our base, large, and huge models outperform all previous generative models across all scales on class-conditional ImageNet benchmarks. Beyond image generation, D-JEPA is well-suited for other continuous data modeling, including video and audio.

## Paper

The full paper can be accessed [here](#). 

## Code

The code implementation of the methods described in the paper can be found [here](#).

## Examples on ImageNet

<script>
    function getRandomIndices(count, max) {
        const indices = new Set();
        while (indices.size < count) {
            indices.add(Math.floor(Math.random() * max).toString().padStart(6, '0'));
        }
        return Array.from(indices);
    }

    const imageIndices = getRandomIndices(16, 142);
    imageIndices.forEach(index => {
        document.write(`<img src="assets/teaser/${index}.png" alt="Random Image from ImageNet Examples" style="width: 150px; height: 150px; margin: 5px;">`);
    });
</script>

## Examples on LJSpeech-1.1

<script>
    const audioFiles = [
        {
            file: 'And it is worth mention in passing that, as an example of fine typography.wav',
            text: 'And it is worth mention in passing that, as an example of fine typography'
        },
        {
            file: 'For although the Chinese took impressions from wood blocks engraved in relief for centuries before the woodcutters of the Netherlands, by a similar process.wav',
            text: 'For although the Chinese took impressions from wood blocks engraved in relief for centuries before the woodcutters of the Netherlands, by a similar process'
        },
        {
            file: 'Has never been surpassed.wav',
            text: 'Has never been surpassed'
        },
        {
            file: 'In being comparatively modern.wav',
            text: 'In being comparatively modern'
        },
        {
            file: 'Now, as all books not primarily intended as picture-books consist principally of types composed to form letterpress.wav',
            text: 'Now, as all books not primarily intended as picture-books consist principally of types composed to form letterpress'
        },
        {
            file: 'Printing, in the only sense with which we are at present concerned, differs from most if not from all the arts and crafts represented in the Exhibition.wav',
            text: 'Printing, in the only sense with which we are at present concerned, differs from most if not from all the arts and crafts represented in the Exhibition'
        },
        {
            file: 'Produced the block books, which were the immediate predecessors of the true printed book.wav',
            text: 'Produced the block books, which were the immediate predecessors of the true printed book'
        },
        {
            file: 'The earliest book printed with movable types, the Gutenberg, or forty-two line Bible of about 1455.wav',
            text: 'The earliest book printed with movable types, the Gutenberg, or forty-two line Bible of about 1455'
        },
        {
            file: 'The earliest book printed with movable types, the Gutenberg, or forty-two line Bible of about fourteen fifty-five.wav',
            text: 'The earliest book printed with movable types, the Gutenberg, or forty-two line Bible of about fourteen fifty-five'
        },
        {
            file: 'The invention of movable metal letters in the middle of the fifteenth century may justly be considered as the invention of the art of printing.wav',
            text: 'The invention of movable metal letters in the middle of the fifteenth century may justly be considered as the invention of the art of printing'
        }
    ];

    audioFiles.forEach(({file, text}) => {
        document.write(`<div><p>${text}</p><audio controls src="assets/audio/${file}"></audio></div>`);
    });
</script>
