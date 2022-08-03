<script lang="ts">
	export let image: string;
	export let imageAlt: string;
	export let heading: string;
	export let text: string;
    export let link: string;
    export let isLast: Boolean=false;
</script>

<a href={link} target="_blank">
<div class="{isLast? "":"border-b border-dashed"} flex items-start gap-x-3 pb-8 ">
    
	<img src={`/images/${image}`} alt={imageAlt} height="85px" width="85px" />

    <div class="grid gap-y-2 text-white tracking-wide">
		<h3>{heading}</h3>
		<p>{text}</p>
	</div>
</div>
</a>