<script>
	import { page } from '$app/stores';

	let submitted = $state(false);

	const categories = {
		facial: {
			title: 'Facial Treatments',
			intro: 'Restore luminosity and firmness with our advanced facial procedures designed to rejuvenate from within.',
			treatments: ['HydraFacial Deluxe', 'Chemical Peels', 'Microneedling with PRP', 'Radiofrequency Skin Tightening'],
			cta: 'Book a facial consultation today.'
		},
		skin: {
			title: 'Skin Therapy',
			intro: 'Target specific skin concerns with evidence-based treatments that deliver visible, lasting results.',
			treatments: ['Laser Resurfacing', 'Pigmentation Correction', 'Acne Scar Treatment', 'Collagen Induction'],
			cta: 'Discover your ideal skin therapy.'
		},
		'hair-removal': {
			title: 'Hair Removal',
			intro: 'Experience smooth, hair-free skin with our precision laser technology and expert care.',
			treatments: ['Diode Laser', 'IPL Photofacial', 'GentleYAG for all skin tones', 'Brazilian & Bikini packages'],
			cta: 'Start your hair removal journey.'
		},
		'hair-health': {
			title: 'Hair Health',
			intro: 'Combat hair loss and stimulate growth with our cutting-edge restoration therapies.',
			treatments: ['PRP Hair Injections', 'Mesotherapy', 'Low-Level Laser Therapy', 'Hair Transplant Referrals'],
			cta: 'Reclaim your confidence with hair restoration.'
		}
	};

	const slug = $derived($page.params.category || 'facial');
	const category = $derived(categories[slug] || categories['facial']);
</script>

<svelte:head>
	<title>{category.title} — HEBE Clinic</title>
</svelte:head>

<section class="bg-alabaster-light py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<span class="section-badge">Treatment</span>
		<h1 class="mt-4 font-serif text-4xl font-bold text-volcanic sm:text-5xl">{category.title}</h1>
		<p class="mt-4 max-w-2xl text-lg text-volcanic-muted">{category.intro}</p>

		<div class="mt-12 grid gap-6 sm:grid-cols-2">
			{#each category.treatments as treatment}
				<div class="santorini-card">
					<h3 class="text-base font-semibold text-volcanic">{treatment}</h3>
				</div>
			{/each}
		</div>

		<div class="mt-16 santorini-card">
			<h3 class="font-serif text-2xl font-bold text-volcanic">Request a Consultation</h3>
			<p class="mt-2 text-sm text-volcanic-muted">{category.cta}</p>
			{#if !submitted}
				<form onsubmit={(e) => { e.preventDefault(); submitted = true; }} class="mt-6 grid gap-4 sm:grid-cols-2">
					<input type="text" placeholder="Full Name" required class="hebe-input sm:col-span-1" />
					<input type="email" placeholder="Email Address" required class="hebe-input sm:col-span-1" />
					<input type="tel" placeholder="Phone Number" required class="hebe-input sm:col-span-1" />
					<textarea placeholder="Tell us about your goals..." rows="4" class="hebe-input sm:col-span-2"></textarea>
					<button type="submit" class="rounded-lg bg-aegean px-6 py-3 text-sm font-semibold text-white transition-colors hover:bg-aegean-dark sm:col-span-2 sm:w-auto">Send Request</button>
				</form>
			{:else}
				<div class="mt-6 rounded-lg bg-aegean/10 p-6 text-center">
					<p class="font-semibold text-aegean">Thank you for your interest!</p>
					<p class="mt-1 text-sm text-volcanic-muted">Our team will contact you within 24 hours.</p>
				</div>
			{/if}
		</div>
	</div>
</section>
