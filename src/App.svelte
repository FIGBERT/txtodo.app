<script>
	import DownloadIcon from "./DownloadIcon.svelte";

	let backgroundColor, textColor, linkColor, appearenceImg, appearenceAlt, phoneImg, borderColor;
	let isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
	$: if (isDarkMode) {
		backgroundColor = "bg-background-dark";
		textColor = "text-white";
		linkColor = "text-link-dark";
		appearenceImg = "./moon.svg";
		appearenceAlt = "switch to light mode";
		phoneImg = "app-dark.png";
		borderColor = "border-gray-800";
	} else {
		backgroundColor = "bg-background-light";
		textColor = "text-black";
		linkColor = "text-link-light";
		appearenceImg = "./sun.svg";
		appearenceAlt = "switch to dark mode";
		phoneImg = "app-light.png";
		borderColor = "border-gray-400";
	}

	let toggleMode = () => {
		isDarkMode = !isDarkMode
	}
</script>

<main>
	<div class="{backgroundColor} min-h-screen w-screen pb-24">
		<div class="pl-5 sm:pl-6 md:pl-8 lg:pl-10">
			<header>
				<button class="float-right m-4" on:click={toggleMode}>
					<img src={appearenceImg} alt={appearenceAlt} class="w-5 sm:w-5 md:w-6 lg:w-8">
				</button>
				<h1 class="{textColor} antialiased font-sans font-hairline tracking-wider text-3xl sm:text-4xl md:text-5xl lg:text-6xl">txtodo</h1>
			</header>
			<div class="flex flex-col lg:flex-row items-center justify-between">
				<div class="mt-16 pb-16 w-7/12 md:w-1/2 lg:w-2/5">
					<h2 class="{textColor} antialiased font-sans font-light tracking-wider text-xs sm:text-sm md:text-base lg:text-lg text-center lg:text-left"><span class="font-bold">txtodo</span> is a minimalist open-source todo list app made by <a href="https://figbert.com/" class="{linkColor}" target="_blank" rel="noopener noreferrer">figbert</a> and inspired by <a href="https://jeffhuang.com/productivity_text_file/" class="{linkColor}" target="_blank" rel="noopener noreferrer">jeff huang.</a></h2>
					<h3 class="text-subtext antialiased font-sans font-light tracking-wider text-xs sm:text-sm md:text-base lg:text-lg text-center lg:text-left">it lists short-term tasks to help you get things done without overthinking it. plus, it's lightweight, open-source, and built with swiftui.</h3>
					<p class="text-subtext antialiased font-sans font-light tracking-wider text-xs mt-8 text-center lg:text-left">txtodo does not track you: it is entirely offline. the only app analytics i receive are provided by the app store. this site uses <a href="https://www.goatcounter.com/" class="text-blue-700">goatcounter</a> for anonymous analytics.</p>
					<div class="mt-8 flex flex-col lg:flex-row items-center lg:items-start">
						<div class="inline-block align-middle mb-3 lg:mb-0 lg:mr-2"><DownloadIcon isDarkMode={isDarkMode} srcPair={["./apple-dark.svg", "./apple-light.svg"]} alt="apple logo" label="download from the app store" link="https://apps.apple.com/us/app/txtodo/id1504609185"/></div>
						<div class="inline-block align-middle"><DownloadIcon isDarkMode={isDarkMode} srcPair={["./github-dark.svg", "./github-light.svg"]} alt="Github logo" label="view the code" link="https://github.com/therealFIGBERT/txtodo"/></div>
					</div>
				</div>
				<img src={phoneImg} alt="txtodo on an iPhone" class="h-auto w-64 object-cover mr-0 lg:mr-32 lg:transform" style="--transform-rotate: 8deg;"/>
			</div>
		</div>
		<div class="mt-16 p-5 border-2 {borderColor} rounded shadow-2xl {textColor} font-thin text-left mx-auto max-w-md md:max-w-lg lg:max-w-xl transform" style="--transform-rotate: -2deg;">
			<div class="text-xs sm:text-sm md:text-base lg:text-lg">
				<p class="opacity-50 {textColor} mb-2">hello,</p>
				<p class="mb-2">i'm <a href="https://figbert.com/" class="{linkColor}" target="_blank" rel="noopener noreferrer">figbert</a> – the developer of txtodo. it's nice to meet you!</p>
				<p class="mb-2">txtodo is built to remedy the problems i've found with the task managers of today – namely, the overwhelming buildup of tasks that we procrastinate, delay, and postpone. the longer the tasks sit in our todo, the less likely they are to be completed.</p>
				<p class="mb-2">with txtodo, this problem is gone – because those delayed tasks are too. it lists short-term tasks to help you get things done, and anything unfinished at the end of the day is discarded so you can start fresh tomorrow.</p>
				<p class="mb-2">feel free to reach out to me with feedback, appreciation, or just to chat at <a href="mailto:txtodo@figbert.com" class="{linkColor}" rel="noopener noreferrer">txtodo@figbert.com</a>.</p>
			</div>
		</div>
	</div>
</main>