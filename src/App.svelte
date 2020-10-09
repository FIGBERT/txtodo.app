<script>
	import DownloadIcon from "./DownloadIcon.svelte";

	let phoneImg, multideviceImg;
	let isDarkMode = window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
	$: if (isDarkMode) {
		phoneImg = "iphone-dark.png";
		multideviceImg = "multidevice-dark.png";
	} else {
		phoneImg = "iphone-light.png";
		multideviceImg = "multidevice-light.png"
	}
</script>

<header>
	<section class="bg-black text-white text-center py-1 text-xs lg:text-lg">txtodo v2.0 out now!</section>
	<h1 class="pl-5 lg:pl-10 font-hairline text-3xl lg:text-6xl">txtodo</h1>
</header>
<main class="w-full sm:w-1/2 lg:w-full mx-0 sm:mx-auto lg:mx-0 grid grid-cols-1 lg:grid-cols-2 grid-rows-4 lg:grid-rows-2 gap-6">
	<section id="ios">
		<h2 class="text-xs lg:text-lg text-center lg:text-left">
			<span class="font-bold">txtodo</span> is a minimalist open-source todo list app made by
			<a href="https://figbert.com/" target="_blank" rel="noopener noreferrer">figbert</a>
			and inspired by
			<a href="https://jeffhuang.com/productivity_text_file/" target="_blank" rel="noopener noreferrer">jeff huang.</a>
		</h2>
		<h3 class="text-xs lg:text-lg text-center lg:text-left">
			it lists short-term tasks to help you get things done without overthinking it. plus, it's lightweight, open-source, and built with swiftui.
		</h3>
		<div class="mt-8 flex flex-col lg:flex-row items-center lg:items-start">
			<div class="inline-block align-middle mb-3 lg:mb-0 lg:mr-2"><DownloadIcon isDarkMode={isDarkMode} srcPair={["./apple-dark.svg", "./apple-light.svg"]} alt="apple logo" label="download the ios app" link="https://apps.apple.com/us/app/txtodo/id1504609185"/></div>
			<div class="inline-block align-middle mb-3 lg:mb-0 lg:mr-2"><DownloadIcon isDarkMode={isDarkMode} srcPair={["./apple-dark.svg", "./apple-light.svg"]} alt="apple logo" label="download the macos app" link="https://apps.apple.com/us/app/txtodo-companion/id1517267304"/></div>
			<div class="inline-block align-middle"><DownloadIcon isDarkMode={isDarkMode} srcPair={["./github-dark.svg", "./github-light.svg"]} alt="github logo" label="view my code" link="https://git.figbert.com/FIGBERT/txtodo.app"/></div>
		</div>
	</section>
	<img src={phoneImg} alt="txtodo running on an iPhone" class="h-auto w-full sm:w-2/3"/>
	<img id="two-img" src={multideviceImg} alt="txtodo running on an iPhone, iPad, and Macbook"/>
	<section id="mac two-text">
		<h2 class="text-xs lg:text-lg text-center lg:text-left">
			txtodo v2.0 brings your tasks to the cloud! now you can install txtodo on your phone and computer for a seamless cross-platform experience.
		</h2>
		<h3 class="text-xs lg:text-lg text-center lg:text-left">
			your tasks are secured with icloud end-to-end encryption, so your todo stays just that: yours.
		</h3>
	</section>
</main>
<section id="note" class="mt-16 mb-12 lg:mb-24 p-5 border-2 rounded shadow-2xl text-left mx-auto max-w-md lg:max-w-xl transform">
	<div class="text-xs lg:text-lg">
		<p class="opacity-50">hello,</p>
		<p>i'm <a href="https://figbert.com/" target="_blank" rel="noopener noreferrer">figbert</a> – the developer of txtodo. it's nice to meet you!</p>
		<p>txtodo is built to remedy the problems i've found with the task managers of today – namely, the overwhelming buildup of tasks that we procrastinate, delay, and postpone. the longer the tasks sit in our todo, the less likely they are to be completed.</p>
		<p>with txtodo, this problem is gone – because those delayed tasks are too. it lists short-term tasks to help you get things done, and anything unfinished at the end of the day is discarded so you can start fresh tomorrow.</p>
		<p>feel free to reach out to me with feedback, appreciation, or just to chat at <a href="mailto:figbert@figbert.com" rel="noopener noreferrer">figbert@figbert.com</a>.</p>
	</div>
</section>
<footer id="privacy" class="mb-2 text-center" style="color: var(--subtext-color); font-size: .5rem;">txtodo does not track you. the only app analytics i receive are automatically provided by the app store. this site uses <a href="https://www.goatcounter.com/">goatcounter</a> for anonymous analytics.</footer>
