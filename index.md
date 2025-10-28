---
layout: default
---

{% include_relative README.md %}

<pre class="mermaid">
    architecture-beta
        group api(azure:app-services)[API]

        service db(logos:aws-aurora)[Database] in api
        service disk1(logos:aws-glacier)[Storage] in api
        service disk2(logos:aws-s3)[Storage] in api
        service server(logos:aws-ec2)[Server] in api

        db:L -- R:server
        disk1:T -- B:server
        disk2:T -- B:db
</pre>

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
