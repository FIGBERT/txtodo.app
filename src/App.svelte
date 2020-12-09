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

<main>
	<section id="ios">
		<header><h1>txtodo</h1></header>
		<h2>
			<span>txtodo</span> is a minimalist open-source todo list app made by
			<a href="https://figbert.com/" target="_blank" rel="noopener noreferrer">figbert</a>
			and inspired by
			<a href="https://jeffhuang.com/productivity_text_file/" target="_blank" rel="noopener noreferrer">jeff huang.</a>
		</h2>
		<h3>
			it lists short-term tasks to help you get things done without overthinking it. plus, it's lightweight, open-source, and built with swiftui.
		</h3>
		<div id="download-container">
			<div><DownloadIcon isDarkMode={isDarkMode} srcPair={["./apple-dark.svg", "./apple-light.svg"]} alt="apple logo" label="download on the app store" link="https://apps.apple.com/us/app/txtodo/id1504609185"/></div>
			<div><DownloadIcon isDarkMode={isDarkMode} srcPair={["./github-dark.svg", "./github-light.svg"]} alt="github logo" label="view my code" link="https://git.figbert.com/FIGBERT/txtodo"/></div>
		</div>
	</section>
	<img id="one-img" src={phoneImg} alt="txtodo running on an iPhone"/>
	<img id="two-img" src={multideviceImg} alt="txtodo running on an iPhone, iPad, and Macbook"/>
	<section id="mac two-text">
		<h2>
			txtodo v3 brings your tasks to the cloud! install txtodo on your phone and computer for a seamless cross-platform experience.
		</h2>
		<h3>
			your tasks are secured with icloud end-to-end encryption, so your todo stays just that: yours.
		</h3>
	</section>
</main>
<section id="note">
	<div>
		<p>hello,</p>
		<p>i'm <a href="https://figbert.com/" target="_blank" rel="noopener noreferrer">figbert</a> – the developer of txtodo. it's nice to meet you!</p>
		<p>txtodo is built to remedy the problems i've found with the task managers of today – namely, the overwhelming buildup of tasks that we procrastinate, delay, and postpone. the longer the tasks sit in our todo, the less likely they are to be completed.</p>
		<p>with txtodo, this problem is gone – because those delayed tasks are too. it lists short-term tasks to help you get things done, and anything unfinished at the end of the day is discarded so you can start fresh tomorrow.</p>
		<p>feel free to reach out to me with feedback, appreciation, or just to chat at <a href="mailto:figbert@figbert.com" rel="noopener noreferrer">figbert@figbert.com</a>.</p>
	</div>
</section>
<footer id="privacy">txtodo does not track you. the only app analytics i receive are built in to the app store. this site uses <a href="https://umami.is/">self-hosted anonymous analytics</a>.</footer>
