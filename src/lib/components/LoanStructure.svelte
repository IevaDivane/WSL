<script lang="ts">
	interface LoanOption {
		id: string;
		description: string;
		icon?: string;
	}

	interface Props {
		loans?: LoanOption[];
		title?: string;
		subtitle: string;
	}

	let {
		title = "How Our Loans Are Structured",
		subtitle = "All facilities are senior secured and designed to protect capital while supporting borrower growth.",
		loans = [
			{
				id: "1",
				icon: "/icons/Key.svg",
				description: "First-ranking security over app store, ad network, platform, publisher, B2B receivables, and/or government tax credits"
			},
			{
				id: "2",
				icon: "/icons/SplitHorizontal.svg",
				description: "Facility terms of 6 to 24 months"
			},
			{
				id: "3",
				icon: "/icons/Vector3.svg",
				description: "Interest rates ranging from 1.75% to 2.5%/mo"
			},
			{
				id: "4",
				icon: "/icons/Vector2.svg",
				description: "Loan sizes between €100k and €5 million"
			},
			{
				id: "5",
				icon: "/icons/Vector.svg",
				description: "Only 0.5% of all-time issued loans written off"
			}
		]
	}: Props = $props();
</script>

<section class="max-w-7xl mx-auto w-full py-16 pb-4 px-4 md:p-16">
	<div class="flex flex-col gap-4">
		<span class="text-xs font-semibold px-2 py-1 w-fit rounded-[20px] text-primary-black border border-[#1B1818]">KEY LOAN CHARACTERISTICS </span>

		<h2 class="text-2xl font-bold text-primary-black leading-[31px] md:text-4xl md:leading-[47px]">{title}</h2>

		<h3 class="text-base font-normal text-secondary-dark-gray leading-[31px] md:max-w-[561px]">{subtitle}</h3>

		<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-6">
			{#each loans as loan, index (loan.id)}
				<div class="rounded-[30px] p-6 flex bg-loan-block gap-4 items-center {index === 0 ? 'md:col-span-2 lg:col-span-2' : ''}">
					{#if loan.icon}
						<img src={loan.icon} alt={loan.description} class="w-12 h-12 object-contain" />
					{/if}
					<p class="text-base text-primary-black font-medium">{loan.description}</p>
					
				</div>
			{/each}
		</div>
	</div>
</section>