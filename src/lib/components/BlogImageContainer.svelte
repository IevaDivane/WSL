<script lang="ts">
	interface Props {
		title?: string;
		subtitle?: string;
		description?: string;
		image?: string;
	}

	let {
		title = "Non-Dilutive Growth Capital",
		subtitle = "Helping studios scale without equity dilution",
		description = "Our loans enable studios to grow revenues and launch new titles without giving up ownership. Many borrowers choose equity only later—after scaling—at higher valuations driven by increased revenue and EBITDA.",
		image = "/images/heila_parks.png"
	}: Props = $props();
</script>

<section class="max-w-7xl mx-auto w-full py-16 px-4 md:p-16">
	<div class="flex flex-col gap-8 md:flex-row md:gap-16">
		{#if image}
			<div class="w-full md:max-w-[508px] overflow-hidden">
				<img src={image} alt={title} class="max-w-[328px] w-full h-auto object-cover md:max-w-[508px] md:h-auto" />
			</div>
		{/if}
		<div class="flex flex-col gap-4 md:justify-center">
			<h2 class="block-title text-left">{title}</h2>
			<h3 class="text-lg md:text-2xl text-left font-medium leading-[23px] text-secondary-dark-gray">{subtitle}</h3>
			{#if description}
				<p class="text-sm text-left text-secondary-dark-gray md:text-base">{description}</p>
			{/if}

			<a href="https://www.google.com/" target="_blank" rel="noopener noreferrer" class="mt-4 w-fit bg-primary-golden-yellow py-[10px] px-5 rounded-[12px] text-base font-semibold leading-5 inline-block text-center">ABOUT OUR ENGINEERING FIRM</a>
		</div>
	</div>
</section>