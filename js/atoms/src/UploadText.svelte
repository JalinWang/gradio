<script lang="ts">
	import { _ } from "svelte-i18n";

	export let type: "video" | "image" | "audio" | "file" | "csv" = "file";

	const defs = {
		image: "upload_text.drop_image",
		video: "upload_text.drop_video",
		audio: "upload_text.drop_audio",
		file: "upload_text.drop_file",
		csv: "upload_text.drop_csv",
	};
</script>

<div class="wrap">
	{$_(defs[type])}
	<span class="or">- {$_("common.or")} -</span>
	{$_("upload_text.click_to_upload")}
</div>

<style>
	.wrap {
		display: flex;
		flex-direction: column;
		justify-content: center;
		min-height: var(--size-60);
		color: var(--block-label-text-color);
		line-height: var(--line-md);
	}

	.or {
		color: var(--body-text-color-subdued);
	}

	@media (--screen-md) {
		.wrap {
			font-size: var(--text-lg);
		}
	}
</style>
