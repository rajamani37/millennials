<script>
	let active = true;
</script>

<div id="splash_screen" class:active>
	<div class="logo">
		<img src="logo.png" alt="Millennials Logo" />
		<!-- <span class="logo-text">Millennials</span> -->
	</div>
	<br />
	<div class="welcome-text">Welcome to 3D Shopping</div>
	<div class="sub-text">Turn up your volume to enjoy an immersive experience</div>
	<div id="loading">
		<div
			id="loading_bar"
			on:click={() => {
				active = false;
			}}
		>
			<div id="loading_fill" />
			<div id="loading_text">Step Inside</div>
		</div>
	</div>
</div>

<style>
	#splash_screen {
		--buttonHeight: 50px;
		--buttonWidth: 200px;

		display: none;
		position: absolute;
		inset: 0;
		height: 100vh;

		flex-direction: column;
		justify-content: center;
		align-items: center;

		background-color: #000;
		animation: fadeIn 1s ease-in-out forwards;
	}

	#splash_screen.active {
		display: flex;
	}

	@keyframes fadeIn {
		from { opacity: 0; }
		to { opacity: 1; }
	}

	.logo {
		display: flex;
		align-items: center;
		gap: 10px;
		margin-bottom: 10px;
	}

	img {
		height: 80px;
	}

	.logo-text {
		color: white;
		font-size: 2.5rem;
		font-family: 'Georgia', serif;
		letter-spacing: 1px;
		text-shadow: 0 0 10px rgba(0, 255, 100, 0.6);
	}

	.welcome-text {
		color: white;
		font-size: 1.8rem;
		font-weight: bold;
		margin-top: 10px;
	}

	.sub-text {
		color: #ddd;
		font-size: 1rem;
		margin: 15px 0 30px 0;
	}

	:global(#loading) {
		display: block;
	}

	#loading_bar {
		position: relative;
		display: flex;
		justify-content: center;
		align-items: center;

		width: var(--buttonWidth);
		height: var(--buttonHeight);

		padding: 2px;
		border: 2px solid #0f0;
		border-radius: 25px;

		transition: all 0.3s ease-in-out;
		background: transparent;
		cursor: pointer;
	}

	:global(#loading_bar) {
		cursor: unset;
		pointer-events: none;
	}

	#loading_bar:hover {
		background-color: #0f0;
		transform: scale(1.05);
	}

	#loading_fill {
		position: absolute;
		left: 0;
		height: 100%;
		background-color: #0f0;
		border-radius: 25px;
		z-index: 0;
	}
	:global(#loading_fill) {
		width: 0;
	}

	#loading_text {
		position: relative;
		color: white;
		font-size: 1rem;
		font-weight: bold;
		z-index: 1;
	}

	:global(#loading_btn) {
		display: none;
	}
</style>
