<script>
    let color;
    let text;
    export { color, text };
</script>

<span class="badge bg-{color == null ? "secondary" : color}">{text}</span>