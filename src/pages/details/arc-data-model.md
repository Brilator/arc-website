---
layout: ../../layouts/MarkdownLayout.astro
title: 'ARC data model'
pubDate: 2024-09-13
description: 'A short description of the ARC data mode.'
author: 'Timo Mühlhaus'
image:
    url: 'https://docs.astro.build/assets/rose.webp'
    alt: 'The Astro logo on a dark background with a pink glow.'
tags: ["RO-Crate", "FAIR digital object","JSON-LD"]
---

ARC is an implementation of a FAIR Digital Object (FDO), utilizing RO-Crate with Schema.org and Bioschemas objects as its foundation, and further enhancing it with additional metadata and structure. An RO-Crate serves as a research object, composed of a collection of research elements and data, enabling detailed descriptions of these collections. Research elements in this context include samples, measurement data, and other research outputs.

![ARC RO-Crate](/arc-website/arc-ro-crate.png)

ARC extends the basic RO-Crate concept by incorporating detailed descriptions of the processes that lead to the generation of data. This enhancement allows the data model to represent a complete process graph, encompassing experimental procedures, simulations, analyses, and the interconnections and provenance among them.
In this model, research elements are the nodes of the process graph, while the connections between them, defined as lab processes, are represented by edges. 

![ARC RO-Crate-Process](/arc-website/ARC-isa-cwl-decorations.png)

To allow for unambiguous inclusion of data entities into the process graph, Data Fragment Selectors, defined by W3, can be used in.
Each process can be further specified and annotated with explanatory and descriptive metadata using lists of PropertyValues, enhancing its clarity and traceability.

![Fragment Selector](/arc-website/data-fragment-selector.png)

The collection of data fragment selectors for a given dataset is called the datamap. In addition to the selectors, the datamap contains additional information about how to read and interpret the content of the data fragments. Besides this, it carries and annotates data resources which do not originate in the process sequence.

![Datamap](/arc-website/datamap.png)

To specialize ARC for biological data, the widely recognized ISA model (Investigation, Study, Assay) is employed, alongside the abstract Common Workflow Language (CWL) for workflows. The ISA model and CWL provide additional layers of metadata and structure, allowing for more precise definitions of processes and data. Dataset objects within ARC can implement either ISA or CWL interface object definitions, ensuring compatibility and standardization across various biological datasets and workflows.

![ARC RO Crate](/arc-website/arc-ro-crate-profiles.png)

This approach elevates ARC from merely documenting research objects to providing a full, interconnected representation of the research process, from data generation to analysis, making it a powerful tool for tracing and reproducing scientific investigations.
