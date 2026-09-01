<script>
	const stats = [
		{ value: '15+', label: 'Years Experience' },
		{ value: '8,000+', label: 'Happy Patients' },
		{ value: '98%', label: 'Satisfaction Rate' },
		{ value: '12+', label: 'Certifications' }
	];

	const credentials = [
		'International Society of Aesthetic Plastic Surgery',
		'European Board of Plastic Surgery',
		'American Academy of Dermatology',
		'Hellenic Society of Aesthetic Medicine',
		'Fellowship in Anti-Aging Medicine',
		'Advanced Laser Surgery Certification'
	];
</script>

<svelte:head>
	<title>About — HEBE Clinic</title>
</svelte:head>

<section class="bg-alabaster-light py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="text-center">
			<span class="section-badge">Our Story</span>
			<h1 class="mt-4 font-serif text-4xl font-bold text-volcanic sm:text-5xl">About HEBE Clinic</h1>
		</div>
		<div class="mt-12 max-w-3xl mx-auto">
			<p class="text-lg leading-relaxed text-volcanic-muted">
				HEBE Clinic was founded on the principle that beauty and wellness are deeply personal journeys. Nestled in the breathtaking landscape of Santorini, our clinic offers a sanctuary where world-class medical expertise meets the tranquil luxury of Greek hospitality.
			</p>
			<p class="mt-6 text-lg leading-relaxed text-volcanic-muted">
				Our team of board-certified specialists brings together decades of experience in aesthetic medicine, dermatology, and plastic surgery. We believe in a holistic approach — combining cutting-edge technology with individualized care to help every patient achieve their best, most confident self.
			</p>
		</div>

		<div class="mt-20 grid gap-8 sm:grid-cols-2 lg:grid-cols-4">
			{#each stats as stat}
				<div class="santorini-card text-center">
					<p class="font-serif text-4xl font-bold text-aegean">{stat.value}</p>
					<p class="mt-2 text-sm text-volcanic-muted">{stat.label}</p>
				</div>
			{/each}
		</div>

		<div class="mt-20">
			<div class="text-center">
				<span class="section-badge">Credentials</span>
				<h2 class="mt-4 font-serif text-3xl font-bold text-volcanic sm:text-4xl">Certifications & Memberships</h2>
			</div>
			<div class="mt-8 flex flex-wrap justify-center gap-3">
				{#each credentials as cert}
					<span class="section-badge">{cert}</span>
				{/each}
			</div>
		</div>
	</div>
</section>
