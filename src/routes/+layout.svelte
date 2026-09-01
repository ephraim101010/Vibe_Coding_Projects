<script>
	import Navbar from '$lib/components/Navbar.svelte';
	import logo from '$lib/assets/hebe2.png?url';
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<title>HEBE Clinic — Santorini Luxury Medical Aesthetics</title>
	<meta name="description" content="Premium medical-aesthetic clinic in Santorini offering advanced facial treatments, skin care, and hair restoration." />
</svelte:head>

<div class="flex min-h-screen flex-col">
	<div class="bg-aegean/95 px-4 py-2 text-center text-xs font-medium text-white sm:text-sm">
		Certified practitioners • Medical-grade treatments • Santorini luxury experience
	</div>
	<Navbar />
	<main class="flex-1">
		{@render children()}
	</main>
	<footer class="border-t border-volcanic-muted/10 bg-alabaster">
		<div class="mx-auto max-w-7xl px-4 py-12 sm:px-6 lg:px-8">
			<div class="grid grid-cols-1 gap-8 sm:grid-cols-2 lg:grid-cols-4">
<div>
				<div class="flex items-center gap-3">
					<img src={logo} alt="HEBE Medical Aesthetic Center" class="h-20 w-auto" />
					<span class="font-serif text-base font-semibold text-volcanic">HEBE Medical Aesthetic Center</span>
				</div>
				<p class="mt-3 text-sm text-volcanic-muted">Luxury medical aesthetics in the heart of Santorini.</p>
			</div>
				<div>
					<h3 class="text-sm font-semibold uppercase tracking-wider text-volcanic">Contact</h3>
					<ul class="mt-3 space-y-2 text-sm text-volcanic-muted">
						<li>09 940825514</li>
						<li>contact@hebeclinic.gr</li>
					</ul>
				</div>
				<div>
					<h3 class="text-sm font-semibold uppercase tracking-wider text-volcanic">Hours</h3>
					<ul class="mt-3 space-y-2 text-sm text-volcanic-muted">
						<li>Mon — Fri: 10:00 — 17:00</li>
						<li>Wed: Closed</li>
						<li>Sat — Sun: 10:00 — 17:00</li>
					</ul>
				</div>
				<div>
					<h3 class="text-sm font-semibold uppercase tracking-wider text-volcanic">Quick Links</h3>
					<ul class="mt-3 space-y-2 text-sm text-volcanic-muted">
						<li><a href="/about" class="transition-colors hover:text-aegean">About</a></li>
						<li><a href="/services" class="transition-colors hover:text-aegean">Services</a></li>
						<li><a href="/contact" class="transition-colors hover:text-aegean">Contact</a></li>
					</ul>
				</div>
			</div>
			<div class="mt-8 border-t border-volcanic-muted/10 pt-8 text-center text-xs text-volcanic-muted">
				&copy; {new Date().getFullYear()} HEBE Clinic. All rights reserved.
			</div>
		</div>
	</footer>
</div>
