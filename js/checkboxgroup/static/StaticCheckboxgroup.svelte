<script lang="ts">
	import CheckboxGroup from "../shared";
	import { Block } from "@gradio/atoms";
	import { StatusTracker } from "@gradio/statustracker";
	import type { LoadingStatus } from "@gradio/statustracker";
	import { _ } from "svelte-i18n";
	export let elem_id = "";
	export let elem_classes: string[] = [];
	export let visible = true;
	export let value: (string | number)[] = [];
	export let value_is_output = false;
	export let choices: [string, number][];
	export let container = true;
	export let scale: number | null = null;
	export let min_width: number | undefined = undefined;
	export let label = $_("checkbox.checkbox_group");
	export let info: string | undefined = undefined;
	export let show_label: boolean;

	export let loading_status: LoadingStatus;
</script>

<Block
	{visible}
	{elem_id}
	{elem_classes}
	type="fieldset"
	{container}
	{scale}
	{min_width}
>
	<StatusTracker {...loading_status} />

	<CheckboxGroup
		bind:value
		bind:value_is_output
		{choices}
		{label}
		{info}
		{show_label}
		on:select
		on:change
		on:input
		disabled
	/>
</Block>
