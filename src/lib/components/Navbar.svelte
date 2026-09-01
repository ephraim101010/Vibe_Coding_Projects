<script>
	import logo from '$lib/assets/hebe2.png?url';
	let mobileOpen = $state(false);
</script>

<nav class="sticky top-0 z-50 border-b border-volcanic-muted/20 bg-alabaster/95 backdrop-blur-md">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<a href="/" class="flex items-center gap-3">
				<img src={logo} alt="HEBE Medical Aesthetic Center" class="h-16 w-auto" />
				<span class="font-serif text-lg font-semibold text-volcanic sm:text-xl">HEBE Medical Aesthetic Center</span>
			</a>

			<div class="hidden items-center gap-8 md:flex">
				<a href="/" class="text-sm font-medium text-volcanic-muted transition-colors hover:text-aegean">Home</a>
				<a href="/about" class="text-sm font-medium text-volcanic-muted transition-colors hover:text-aegean">About</a>
				<a href="/services" class="text-sm font-medium text-volcanic-muted transition-colors hover:text-aegean">Services</a>
				<a href="/contact" class="rounded-lg bg-aegean px-5 py-2.5 text-sm font-semibold text-white transition-colors hover:bg-aegean-dark">
					Book Consultation
				</a>
			</div>

			<button
				onclick={() => mobileOpen = !mobileOpen}
				class="rounded-lg p-2 text-volcanic-muted transition-colors hover:text-aegean md:hidden"
				aria-label="Toggle menu"
			>
				<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					{#if mobileOpen}
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
					{:else}
						<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
					{/if}
				</svg>
			</button>
		</div>

		{#if mobileOpen}
			<div class="border-t border-volcanic-muted/10 pb-4 pt-2 md:hidden">
				<div class="flex flex-col gap-2">
					<a href="/" onclick={() => mobileOpen = false} class="rounded-lg px-4 py-2 text-sm font-medium text-volcanic-muted transition-colors hover:bg-alabaster-light hover:text-aegean">Home</a>
					<a href="/about" onclick={() => mobileOpen = false} class="rounded-lg px-4 py-2 text-sm font-medium text-volcanic-muted transition-colors hover:bg-alabaster-light hover:text-aegean">About</a>
					<a href="/services" onclick={() => mobileOpen = false} class="rounded-lg px-4 py-2 text-sm font-medium text-volcanic-muted transition-colors hover:bg-alabaster-light hover:text-aegean">Services</a>
					<a href="/contact" onclick={() => mobileOpen = false} class="mt-2 rounded-lg bg-aegean px-4 py-2.5 text-center text-sm font-semibold text-white transition-colors hover:bg-aegean-dark">Book Consultation</a>
				</div>
			</div>
		{/if}
	</div>
</nav>
