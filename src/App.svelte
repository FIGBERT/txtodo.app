<script>
	import DownloadIcon from "./DownloadIcon.svelte";

	let backgroundColor, textColor, linkColor, appearenceImg, appearenceAlt, phoneImg;
	let isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
	$: if (isDarkMode) {
		backgroundColor = "bg-background-dark";
		textColor = "text-white";
		linkColor = "text-link-dark";
		appearenceImg = "./moon.svg";
		appearenceAlt = "switch to light mode";
		phoneImg = "./app-dark.png";
	} else {
		backgroundColor = "bg-background-light";
		textColor = "text-black";
		linkColor = "text-link-light";
		appearenceImg = "./sun.svg";
		appearenceAlt = "switch to dark mode";
		phoneImg = "./app-light.png"
	}

	let toggleMode = () => {
		isDarkMode = !isDarkMode
	}
</script>

<main>
	<div class="bg-no-repeat bg-bottom md:bg-right-bottom bg-bottomcuttof md:bg-rightside bg-fixed {backgroundColor} h-screen w-screen pl-5 sm:pl-6 md:pl-8 lg:pl-10 overflow-hidden" style="background-image: url({phoneImg});">
		<header>
			<button class="float-right m-4" on:click={toggleMode}>
				<img src={appearenceImg} alt={appearenceAlt} class="w-5 sm:w-5 md:w-6 lg:w-8">
			</button>
			<h1 class="{textColor} antialiased font-sans font-hairline tracking-wider text-3xl sm:text-4xl md:text-5xl lg:text-6xl">txtodo</h1>
		</header>
		<div class="mt-16 pb-16">
			<h2 class="{textColor} antialiased font-sans font-light tracking-wider text-xs sm:text-sm md:text-base lg:text-lg"><span class="font-bold">txtodo</span> is a simple, minimalist open-source todo app<br/>made by <a href="https://figbert.com/" class="{linkColor}">FIGBERT</a> and inspired by <a href="https://jeffhuang.com/productivity_text_file/" class="{linkColor}">Jeff Huang.</a></h2>
			<h3 class="text-subtext antialiased font-sans font-light tracking-wider text-xs sm:text-sm md:text-base lg:text-lg">It manages immediate, short-term tasks<br/>to help you get things done without overthinking them.<br/>Plus, it's entirely open source, and built with SwiftUI.</h3>
			<div class="mt-16 w-2/3 sm:w-1/2 md:w-2/5 lg:w-1/3 flex justify-around">
				<DownloadIcon isDarkMode={isDarkMode} srcPair={["./apple-dark.svg", "./apple-light.svg"]} alt="Apple logo" label="Download from the App Store" link="https://apple.com/"/>
				<DownloadIcon isDarkMode={isDarkMode} srcPair={["./github-dark.svg", "./github-light.svg"]} alt="Github logo" label="View the repo" link="https://github.com/therealFIGBERT/txtodo"/>
			</div>
		</div>
		
	</div>
</main>