<script lang="ts">
	import { cn } from "../../../lib/utils";
	import type { HTMLHeadingElement } from "svelte/elements";

	type $$Props = HTMLHeadingElement;

	let className: $$Props["class"] = undefined;
	export { className as class };
</script>

<h3
	class={cn("text-lg font-semibold leading-none tracking-tight", className)}
	{...$$restProps}
>
	<slot />
</h3>