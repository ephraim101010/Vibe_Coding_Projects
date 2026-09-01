<script>
	let openIndex = $state(null);

	const faqs = [
		{ q: 'How long does a treatment take?', a: 'Most treatments range from 30 minutes to 2 hours depending on the procedure and area being treated.' },
		{ q: 'Is there any downtime?', a: 'Most of our treatments have minimal to no downtime. We will provide detailed aftercare instructions during your consultation.' },
		{ q: 'Are the results permanent?', a: 'Results vary by treatment. Some are long-lasting with proper maintenance, while others may require periodic touch-ups.' },
		{ q: 'Do you offer financing options?', a: 'Yes, we offer flexible payment plans for comprehensive treatment packages. Please contact us for details.' }
	];
</script>

<svelte:head>
	<title>Services — HEBE Clinic</title>
</svelte:head>

<section class="bg-alabaster-light py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="text-center">
			<span class="section-badge">Treatments</span>
			<h1 class="mt-4 font-serif text-4xl font-bold text-volcanic sm:text-5xl">Our Services</h1>
			<p class="mt-4 max-w-2xl mx-auto text-lg text-volcanic-muted">Discover our comprehensive range of medical-aesthetic treatments, designed to enhance your natural beauty.</p>
		</div>

		<!-- Pricing Table -->
		<div class="mt-16 grid gap-8 lg:grid-cols-3">
			<div class="santorini-card flex flex-col">
				<div class="text-center">
					<h3 class="text-lg font-semibold text-volcanic">Essential</h3>
					<p class="mt-2 text-sm text-volcanic-muted">Single treatment sessions</p>
					<p class="mt-4 font-serif text-3xl font-bold text-aegean">From &euro;150</p>
				</div>
				<ul class="mt-6 flex-1 space-y-3 text-sm text-volcanic-muted">
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Facial consultation</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Single skin treatment</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Basic laser session</li>
				</ul>
				<a href="/contact" class="mt-6 block rounded-lg border border-aegean text-center py-3 text-sm font-semibold text-aegean transition-colors hover:bg-aegean/5">Enquire</a>
			</div>
			<div class="santorini-card flex flex-col border-aegean/30">
				<div class="text-center">
					<span class="inline-block rounded-full bg-sunset/10 px-3 py-1 text-xs font-semibold text-sunset">Popular</span>
					<h3 class="mt-2 text-lg font-semibold text-volcanic">Signature</h3>
					<p class="mt-2 text-sm text-volcanic-muted">Comprehensive packages</p>
					<p class="mt-4 font-serif text-3xl font-bold text-aegean">From &euro;450</p>
				</div>
				<ul class="mt-6 flex-1 space-y-3 text-sm text-volcanic-muted">
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Complete facial package</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Multi-area laser treatment</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Follow-up sessions</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Skincare product kit</li>
				</ul>
				<a href="/contact" class="mt-6 block rounded-lg bg-aegean text-center py-3 text-sm font-semibold text-white transition-colors hover:bg-aegean-dark">Book Now</a>
			</div>
			<div class="santorini-card flex flex-col">
				<div class="text-center">
					<h3 class="text-lg font-semibold text-volcanic">Luxury</h3>
					<p class="mt-2 text-sm text-volcanic-muted">Full transformation programs</p>
					<p class="mt-4 font-serif text-3xl font-bold text-aegean">From &euro;1,200</p>
				</div>
				<ul class="mt-6 flex-1 space-y-3 text-sm text-volcanic-muted">
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> All-inclusive treatment plan</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> VIP concierge service</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Unlimited follow-ups (12mo)</li>
					<li class="flex items-center gap-2"><span class="text-aegean">&#10003;</span> Personalized skincare regimen</li>
				</ul>
				<a href="/contact" class="mt-6 block rounded-lg border border-aegean text-center py-3 text-sm font-semibold text-aegean transition-colors hover:bg-aegean/5">Enquire</a>
			</div>
		</div>

		<!-- FAQ -->
		<div class="mt-24">
			<div class="text-center">
				<span class="section-badge">FAQ</span>
				<h2 class="mt-4 font-serif text-3xl font-bold text-volcanic sm:text-4xl">Common Questions</h2>
			</div>
			<div class="mt-12 max-w-3xl mx-auto space-y-4">
				{#each faqs as faq, i}
					<div class="santorini-card">
						<button
							onclick={() => openIndex = openIndex === i ? null : i}
							class="flex w-full items-center justify-between text-left"
						>
							<span class="text-base font-semibold text-volcanic">{faq.q}</span>
							<svg class="h-5 w-5 shrink-0 text-volcanic-muted transition-transform duration-200 {openIndex === i ? 'rotate-180' : ''}" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
							</svg>
						</button>
						{#if openIndex === i}
							<p class="mt-3 text-sm text-volcanic-muted">{faq.a}</p>
						{/if}
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
