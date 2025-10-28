---
layout: default
---

{% include_relative README.md %}

<script type="module">
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@11/dist/mermaid.esm.min.mjs';
    mermaid.initialize({ startOnLoad: true });
    mermaid.registerIconPacks([
    {
        name: 'azure',
        loader: () =>
        fetch('https://raw.githubusercontent.com/craigles/Documentation/refs/heads/main/azure-icons.json').then((res) => res.json()),
    },
    ]);
</script>
