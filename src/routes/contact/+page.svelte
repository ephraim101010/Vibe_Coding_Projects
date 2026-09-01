<script>
	let submitted = $state(false);

	const categories = [
		{ value: 'facial', label: 'Facial Treatments' },
		{ value: 'skin', label: 'Skin Therapy' },
		{ value: 'hair-removal', label: 'Hair Removal' },
		{ value: 'hair-health', label: 'Hair Health' }
	];
</script>

<svelte:head>
	<title>Contact — HEBE Clinic</title>
</svelte:head>

<section class="bg-alabaster-light py-20">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="text-center">
			<span class="section-badge">Get in Touch</span>
			<h1 class="mt-4 font-serif text-4xl font-bold text-volcanic sm:text-5xl">Contact Us</h1>
			<p class="mt-4 text-lg text-volcanic-muted">We would love to hear from you. Reach out to schedule your consultation.</p>
		</div>

		<div class="mt-16 grid gap-12 lg:grid-cols-2">
			<div>
				<div class="santorini-card">
					<h3 class="text-lg font-semibold text-volcanic">Booking No</h3>
					<p class="mt-1 text-sm text-volcanic-muted">Call us to book your appointment</p>
					<p class="mt-2 font-semibold text-aegean">09 940825514</p>
				</div>
				<div class="mt-6 santorini-card">
					<h3 class="text-lg font-semibold text-volcanic">Clinic Hours</h3>
					<ul class="mt-2 space-y-1 text-sm text-volcanic-muted">
						<li>Monday — Friday: 10:00 AM — 5:00 PM</li>
						<li>Wednesday: Closed</li>
						<li>Saturday — Sunday: 10:00 AM — 5:00 PM</li>
					</ul>
				</div>
				<div class="mt-6 santorini-card">
					<h3 class="text-lg font-semibold text-volcanic">Location</h3>
					<p class="mt-1 text-sm text-volcanic-muted">Room (1), Building (17), Shwe Ohn Pin Housing (1), Yan Aye Road, Yankin Township.</p>
					<p class="mt-1 text-xs text-volcanic-muted">Directions: Enter the Shwe Ohn Pin Housing (1) compound, turn right at the first intersecting street, and follow the directional signage next to "Shwe Tharr Pharmacy".</p>
				</div>
			</div>

			<div class="santorini-card">
				{#if !submitted}
					<form onsubmit={(e) => { e.preventDefault(); submitted = true; }} class="space-y-4">
						<div>
							<label for="name" class="block text-sm font-medium text-volcanic">Name</label>
							<input id="name" type="text" required class="hebe-input mt-1" />
						</div>
						<div>
							<label for="phone" class="block text-sm font-medium text-volcanic">Phone</label>
							<input id="phone" type="tel" required class="hebe-input mt-1" />
						</div>
						<div>
							<label for="email" class="block text-sm font-medium text-volcanic">Email</label>
							<input id="email" type="email" required class="hebe-input mt-1" />
						</div>
						<div>
							<label for="service" class="block text-sm font-medium text-volcanic">Service</label>
							<select id="service" class="hebe-input mt-1">
								<option value="">Select a service</option>
								{#each categories as cat}
									<option value={cat.value}>{cat.label}</option>
								{/each}
							</select>
						</div>
						<div>
							<label for="date" class="block text-sm font-medium text-volcanic">Preferred Date</label>
							<input id="date" type="date" class="hebe-input mt-1" />
						</div>
						<div>
							<label for="message" class="block text-sm font-medium text-volcanic">Message</label>
							<textarea id="message" rows="4" class="hebe-input mt-1"></textarea>
						</div>
						<button type="submit" class="rounded-lg bg-aegean px-6 py-3 text-sm font-semibold text-white transition-colors hover:bg-aegean-dark">Send Inquiry</button>
					</form>
				{:else}
					<div class="flex flex-col items-center justify-center py-12 text-center">
						<div class="mx-auto mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-aegean/10">
							<svg class="h-8 w-8 text-aegean" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
							</svg>
						</div>
						<p class="text-lg font-semibold text-volcanic">Inquiry Sent!</p>
						<p class="mt-2 text-sm text-volcanic-muted">Thank you for reaching out. We will get back to you within 24 hours.</p>
					</div>
				{/if}
			</div>
		</div>
	</div>
</section>
