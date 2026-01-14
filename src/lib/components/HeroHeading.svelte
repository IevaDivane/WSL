<script lang="ts">
	interface InfoBlock {
		icon?: string;
		title: string;
		text: string;
	}

	interface Props {
		title?: string;
		subtitle?: string;
		backgroundImage?: string;
		blocks?: InfoBlock[];
	}

	let { 
		title = "Welcome", 
		subtitle = "Your trusted financial partner",
		backgroundImage,
		blocks = [
			{
				icon: "/icons/CirclesThreePlus.svg",
				title: "Engineering Challenges",
				text: "We develop cutting-edge engineering projects through extensive expertise in the renewable energy sector and a reliable global network."
			},
			{
				icon: "/icons/Stack.svg",
				title: "Innovative  Evaluation",
				text: "At our company, we specialize in innovative engineering solutions, leveraging our deep knowledge of renewable energy and a strong international network. "
			}
		]
	}: Props = $props();

	const backgroundStyle = $derived(
		backgroundImage 
			? `background: linear-gradient(180deg, rgba(0, 0, 0, 0.60) 72.22%, rgba(255, 255, 255, 0.00) 100%), linear-gradient(180deg, rgba(243, 238, 238, 0.00) 0%, rgba(243, 238, 238, 0.00) 33.41%, rgba(243, 238, 238, 0.27) 77.95%, rgba(243, 238, 238, 0.80) 86.31%, #F3EEEE 96.51%), url(${backgroundImage}) lightgray 50% / cover no-repeat; background-blend-mode: darken, normal, normal;`
			: ''
	);
</script>

<section 
	class="w-full text-center relative"
	style={backgroundStyle}
>
	
	<!-- Content -->
	<div class="max-w-7xl mx-auto relative z-10 pt-[108px] min-h-[852px] md:min-h-auto md:pt-[150px] md:px-[190px] md:pb-[186px] p-4 flex flex-col gap-[78px] items-center justify-start md:justify-center">
		<h1 class="text-[32px] md:text-5xl font-bold max-w-[800px] text-primary-off-white">{title}</h1>
		
		<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
			{#each blocks as block, index}
				<div class="flex flex-col h-fit items-left rounded-[30px] gap-2 p-6 bg-block-overlay max-w-[438px] {index === 1 ? 'md:mt-16' : ''}">
					<div class="flex md:flex-col gap-3 items-center">
						{#if block.icon}
							<div class="py-[5px]">
								<img src={block.icon} alt={block.title} class="w-8 h-8 object-contain " />
							</div>
						{/if}
						<h3 class="text-lg md:text-2xl font-semibold text-primary-off-white text-left">{block.title}</h3>
					</div>
					<p class="text-sm md:text-lg text-primary-off-white text-left">{block.text}</p>
				</div>
			{/each}
		</div>
	</div>
</section>