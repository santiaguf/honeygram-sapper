<script context="module">
    export async function preload() {
        let data = {};
        const response = await this.fetch(`https://gist.githubusercontent.com/santiaguf/7145eaeaef5a5454fc461f108cdbf0d7/raw/8761072d683309b771cf11622cb7fc08ec1c8da2/fake-api-honeygram`);
        data = await response.json();
        return { data };
    }
</script>

<script>
    import Header from '../components/Header.svelte';
    import Main from '../components/Main.svelte';
    import Sidebar from '../components/Sidebar.svelte';
    import Timeline from '../components/Timeline.svelte';
    export let data = {};
</script>

<svelte:head>
    <title>Michigram</title>
</svelte:head>

<Main>
    <Timeline posts={data.posts} />
    <Sidebar {...data.user} />
</Main>