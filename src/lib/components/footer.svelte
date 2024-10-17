<script>

	import {  blur, fade, slide } from 'svelte/transition';

	export let bgColor = '#f8f8f8'
	let expand = false;

	function actionWhenInViewport(e) {
		const observer = new IntersectionObserver((entries) => {
			if (entries[0].isIntersecting) {
				// element in viewport
				entries[0].target.style.filter = 'blur(0)';
			} else {
          		entries[0].target.style.filter = 'blur(10px)';
        	}
		});

		observer.observe(e);
	}
</script>

<div class="footer" style="background-color: {bgColor};">
	<div class="background-blur"></div>
	<div use:actionWhenInViewport  class="center-text-large blur-effect">
		<div class="starter">
			<span>Would you want a </span><br /><span class="proj"> project with us?</span>
		</div>
		LET'S GET IN<br /> TOUCH
		<div class="ender">
			<span>We can make sure the</span><br /><span class="proj">best quality of a product</span>
		</div>
		<div class="footer-content flex justify-around mt-[-5rem]" style="align-items: center;">
			<div style="font-size: 1.3rem; font-weight: 200; line-height: 120%;" class="contact">
				<div class="phone">+92&nbsp;319&nbsp;6021977</div>
				<div class="email">info@retrohood.com</div>
			</div>
			<div
				style="font-size: 1.2rem; font-weight: 500; gap: 2rem;"
				class="socials flex justify-center"
			>
				<div><a href="#">Facebook</a></div>
				<div><a href="#">Instagram</a></div>
				<div><a href="#">LinkedIn</a></div>
			</div>
			<div style="font-size: 1.3rem; font-weight: 200;" class="copyright">
				&copy; 2024 Retrohood
			</div>
		</div>
	</div>
</div>

<!-- whatsapp icon -->
<div class="relative">


	{#if expand}

	<div 
		in:fade
		class="exapandable">

		<button class="z-20 text-white flex flex-col shrink-0 grow-0 justify-around 
					fixed bottom-40 right-0 right-5 rounded-lg
					mr-1 mb-5 lg:mr-5 lg:mb-5 xl:mr-10 xl:mb-10">
	  <div class="p-3 rounded-full border-2 border-white bg-blue-600 hover:bg-blue-700">
		
			<svg id='Discord_24' width='36' height='36' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'><rect width='24' height='24' stroke='none' fill='#000000' opacity='0'/>


				<g transform="matrix(0.45 0 0 0.45 12 12)" >
				<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(140,158,255); fill-rule: nonzero; opacity: 1;" transform=" translate(-24, -24)" d="M 40 12 C 40 12 35.415 8.411999999999999 30 8 L 29.512 8.975999999999999 C 34.408 10.174 36.654 11.891 39 14 C 34.955 11.935 30.961 10 24 10 C 17.039 10 13.045 11.935 9 14 C 11.346 11.891 14.018 9.985 18.488 8.975999999999999 L 18 8 C 12.318999999999999 8.537 8 12 8 12 C 8 12 2.8789999999999996 19.425 2 34 C 7.162 39.953 15 40 15 40 L 16.639 37.815 C 13.857 36.848 10.715 35.121 8 32 C 11.238 34.45 16.125 37 24 37 C 31.875 37 36.762 34.45 40 32 C 37.285 35.121 34.143 36.848 31.361 37.815 L 33 40 C 33 40 40.838 39.953 46 34 C 45.121 19.425 40 12 40 12 z M 17.5 30 C 15.567 30 14 28.209 14 26 C 14 23.791 15.567 22 17.5 22 C 19.433 22 21 23.791 21 26 C 21 28.209 19.433 30 17.5 30 z M 30.5 30 C 28.567 30 27 28.209 27 26 C 27 23.791 28.567 22 30.5 22 C 32.433 22 34 23.791 34 26 C 34 28.209 32.433 30 30.5 30 z" stroke-linecap="round" />
				</g>
				</svg>


	  </div>
  
	</button>

		<button class="z-20 text-white flex flex-col shrink-0 grow-0 justify-around 
					fixed bottom-20 right-0 right-5 rounded-lg
					mr-1 mb-5 lg:mr-5 lg:mb-5 xl:mr-10 xl:mb-10">
	  <div class="p-3 rounded-full border-2 border-white bg-green-600 hover:bg-green-700">
		
		<svg id='WhatsApp_24' width='36' height='36' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'><rect width='24' height='24' stroke='none' fill='#000000' opacity='0'/>


			<g transform="matrix(0.42 0 0 0.42 12 12)" >
			<g style="" >
			<g transform="matrix(1 0 0 1 -0.07 0.15)" >
			<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(255,255,255); fill-rule: nonzero; opacity: 1;" transform=" translate(-23.93, -24.15)" d="M 4.868 43.303 L 7.562 33.467999999999996 C 5.9 30.59 5.026 27.324 5.027 23.979 C 5.032 13.514 13.548 5 24.014 5 C 29.093 5.002 33.859 6.979 37.444 10.565999999999999 C 41.028000000000006 14.154 43.002 18.921999999999997 43 23.994 C 42.996 34.459 34.478 42.974000000000004 24.014 42.974000000000004 C 24.012999999999998 42.974000000000004 24.014 42.974000000000004 24.014 42.974000000000004 L 24.006 42.974000000000004 C 20.829 42.973000000000006 17.706 42.176 14.933 40.663000000000004 L 4.868 43.303 z" stroke-linecap="round" />
			</g>
			<g transform="matrix(1 0 0 1 -0.07 0.15)" >
			<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(255,255,255); fill-rule: nonzero; opacity: 1;" transform=" translate(-23.93, -24.15)" d="M 4.868 43.803 C 4.736000000000001 43.803 4.6080000000000005 43.751 4.513 43.654999999999994 C 4.388 43.52799999999999 4.3389999999999995 43.342999999999996 4.386 43.172 L 7.025 33.536 C 5.389 30.630000000000003 4.526 27.330000000000002 4.5280000000000005 23.980000000000004 C 4.532 13.238 13.273 4.5 24.014 4.5 C 29.224 4.502 34.119 6.531000000000001 37.798 10.213000000000001 C 41.477000000000004 13.896 43.502 18.79 43.5 23.994 C 43.496 34.735 34.754 43.474000000000004 24.014 43.474000000000004 C 20.825 43.473000000000006 17.669999999999998 42.68600000000001 14.87 41.197 L 4.994999999999999 43.786 C 4.953 43.798 4.911 43.803 4.868 43.803 z" stroke-linecap="round" />
			</g>
			<g transform="matrix(1 0 0 1 -0.07 0.15)" >
			<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(207,216,220); fill-rule: nonzero; opacity: 1;" transform=" translate(-23.93, -24.15)" d="M 24.014 5 C 29.093 5.002 33.859 6.979 37.444 10.565999999999999 C 41.028000000000006 14.154 43.002 18.921999999999997 43 23.994 C 42.996 34.459 34.478 42.974000000000004 24.014 42.974000000000004 L 24.006 42.974000000000004 C 20.829 42.973000000000006 17.706 42.176 14.933 40.663000000000004 L 4.868 43.303 L 7.562 33.467999999999996 C 5.9 30.59 5.026 27.324 5.027 23.979 C 5.032 13.514 13.548 5 24.014 5 M 24.014 42.974 C 24.014 42.974 24.014 42.974 24.014 42.974 C 24.014 42.974 24.014 42.974 24.014 42.974 M 24.014 42.974 C 24.014 42.974 24.014 42.974 24.014 42.974 C 24.014 42.974 24.014 42.974 24.014 42.974 M 24.014 4 C 24.014 4 24.014 4 24.014 4 C 12.998 4 4.032 12.962 4.027 23.979 C 4.026 27.346 4.876 30.663999999999998 6.4879999999999995 33.601 L 3.9029999999999996 43.04 C 3.8089999999999997 43.385 3.9049999999999994 43.753 4.157 44.007 C 4.347 44.199 4.604 44.303999999999995 4.868 44.303999999999995 C 4.953 44.303999999999995 5.038 44.29299999999999 5.122 44.270999999999994 L 14.809 41.730999999999995 C 17.637 43.199 20.807 43.974 24.006 43.974999999999994 C 35.03 43.974999999999994 43.995999999999995 35.01199999999999 44.001000000000005 23.994999999999994 C 44.00300000000001 18.65599999999999 41.926 13.635999999999994 38.153000000000006 9.859999999999994 C 34.378 6.083 29.357 4.002 24.014 4 L 24.014 4 z" stroke-linecap="round" />
			</g>
			<g transform="matrix(1 0 0 1 0.01 -0.01)" >
			<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(64,195,81); fill-rule: nonzero; opacity: 1;" transform=" translate(-24.01, -23.99)" d="M 35.176 12.832 C 32.196000000000005 9.850000000000001 28.235000000000003 8.207 24.019000000000002 8.206 C 15.315000000000001 8.206 8.236000000000002 15.282 8.232000000000001 23.979999999999997 C 8.231000000000002 26.961 9.065000000000001 29.862999999999996 10.645000000000001 32.376 L 11.021 32.973 L 9.426 38.794 L 15.399000000000001 37.227999999999994 L 15.976 37.56999999999999 C 18.398 39.007999999999996 21.176000000000002 39.767999999999994 24.008000000000003 39.76899999999999 L 24.014000000000003 39.76899999999999 C 32.712 39.76899999999999 39.791000000000004 32.69199999999999 39.794000000000004 23.99299999999999 C 39.795 19.778 38.156 15.814 35.176 12.832 z" stroke-linecap="round" />
			</g>
			<g transform="matrix(1 0 0 1 0.01 0.16)" >
			<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(255,255,255); fill-rule: evenodd; opacity: 1;" transform=" translate(-24.01, -24.16)" d="M 19.268 16.045 C 18.913 15.255000000000003 18.539 15.239 18.2 15.225000000000001 C 17.923 15.213000000000001 17.607 15.214000000000002 17.291 15.214000000000002 C 16.975 15.214000000000002 16.461000000000002 15.333000000000002 16.026 15.808000000000002 C 15.591 16.283 14.365 17.430000000000003 14.365 19.764000000000003 C 14.365 22.098000000000003 16.065 24.354000000000003 16.302 24.67 C 16.538999999999998 24.986 19.584 29.929000000000002 24.406 31.831000000000003 C 28.412999999999997 33.411 29.229 33.097 30.098999999999997 33.018 C 30.968999999999998 32.939 32.906 31.871000000000002 33.300999999999995 30.763 C 33.696 29.655 33.696 28.706000000000003 33.577999999999996 28.508000000000003 C 33.458999999999996 28.310000000000002 33.142999999999994 28.192000000000004 32.669 27.954000000000004 C 32.195 27.716000000000005 29.862 26.569000000000003 29.426999999999996 26.411000000000005 C 28.991999999999997 26.253000000000004 28.675999999999995 26.174000000000007 28.358999999999995 26.649000000000004 C 28.042999999999996 27.123000000000005 27.133999999999993 28.192000000000004 26.856999999999996 28.508000000000003 C 26.579999999999995 28.825000000000003 26.302999999999997 28.865000000000002 25.828999999999997 28.627000000000002 C 25.354999999999997 28.389000000000003 23.826999999999998 27.889000000000003 22.013999999999996 26.273000000000003 C 20.603999999999996 25.016000000000002 19.651999999999994 23.463000000000005 19.374999999999996 22.988000000000003 C 19.097999999999995 22.514000000000003 19.344999999999995 22.257 19.582999999999995 22.020000000000003 C 19.795999999999996 21.807000000000002 20.056999999999995 21.466000000000005 20.294999999999995 21.189000000000004 C 20.531999999999993 20.912000000000003 20.610999999999994 20.714000000000002 20.768999999999995 20.398000000000003 C 20.926999999999996 20.081000000000003 20.847999999999995 19.804000000000002 20.728999999999996 19.567000000000004 C 20.612 19.329 19.69 16.983 19.268 16.045 z" stroke-linecap="round" />
			</g>
			</g>
			</g>
			</svg>
	  </div>
  
	</button>
	</div>
	{/if}


	<button 
		on:click={()=>expand=!expand}
		class="z-20 text-white flex flex-col shrink-0 grow-0 justify-around 
					fixed bottom-0 right-0 right-5 rounded-lg
					mr-1 mb-5 lg:mr-5 lg:mb-5 xl:mr-10 xl:mb-10">
	  <div class="p-3 rounded-full border-2 border-white bg-red-600 hover:bg-red-700">
			{#if !expand}
			<svg transition:slide style="rotate: 180deg;" id='Expand_Arrow_24' width='24' height='24' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'><rect width='24' height='24' stroke='none' fill='#fff' opacity='0'/>
				<g transform="matrix(0.48 0 0 0.48 12 12)" >
				<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(255,255,255); fill-rule: nonzero; opacity: 1;" transform=" translate(-25, -24.99)" d="M 44.988281 13.984375 C 44.726563 13.992188 44.476563 14.101563 44.292969 14.292969 L 25 33.585938 L 5.707031 14.292969 C 5.519531 14.097656 5.261719 13.992188 4.992188 13.988281 C 4.582031 13.992188 4.21875 14.238281 4.0625 14.613281 C 3.910156 14.992188 4 15.421875 4.292969 15.707031 L 24.292969 35.707031 C 24.683594 36.097656 25.316406 36.097656 25.707031 35.707031 L 45.707031 15.707031 C 46.003906 15.421875 46.09375 14.980469 45.9375 14.601563 C 45.777344 14.222656 45.402344 13.976563 44.988281 13.984375 Z" stroke-linecap="round" />
				</g>
			</svg>
			{:else}
			<svg transition:slide id='Multiply_24' width='24' height='24' viewBox='0 0 24 24' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'><rect width='24' height='24' stroke='none' fill='#000000' opacity='0'/>


				<g transform="matrix(1.3 0 0 1.3 12 12)" >
				<path style="stroke: none; stroke-width: 1; stroke-dasharray: none; stroke-linecap: butt; stroke-dashoffset: 0; stroke-linejoin: miter; stroke-miterlimit: 4; fill: rgb(255,255,255); fill-rule: nonzero; opacity: 1;" transform=" translate(-12, -12)" d="M 5.7070312 4.2929688 L 4.2929688 5.7070312 L 10.585938 12 L 4.2929688 18.292969 L 5.7070312 19.707031 L 12 13.414062 L 18.292969 19.707031 L 19.707031 18.292969 L 13.414062 12 L 19.707031 5.7070312 L 18.292969 4.2929688 L 12 10.585938 L 5.7070312 4.2929688 z" stroke-linecap="round" />
				</g>
				</svg>
			{/if}
	  </div>
  
	</button>
  </div>

<style>
	.footer {
		position: relative;
	}
	.background-blur {
		width: 100%;
		background-color: rgba(220, 20, 20, 0.85);
		height: 80vh;
		border-radius: 45%;
		margin-top: 8rem;
		margin-left: 0;
		margin-right: 0;
		filter: blur(10rem);
		position: absolute;
		left: 0;
		right: 0;
		text-align: center;
	}
	.center-text-large {
		height: 100vh;
		text-align: center;
		align-content: center;
		position: relative;
		color: #e2e2e2;
		font-weight: 700;
		font-size: 6rem;
		line-height: 95%;
	}

	.starter {
		color: #e2e2e2;
		font-weight: 500;
		font-size: x-large;
		line-height: 85%;
		padding-bottom: 5rem;
		padding-right: 10rem;
	}

	.starter > .proj {
		margin-right: 1.3rem;
	}

	.ender {
		color: #e2e2e2;
		font-weight: 200;
		font-size: 1.2rem;
		line-height: 85%;
		padding-top: 5rem;
		padding-left: 30rem;
		margin-bottom: 8rem;
	}

	.ender > .proj {
		margin-left: 1.3rem;
	}

	.footer-content {
		color: #e2e2e2;
	}

	.blur-effect {
    transition: filter 2s ease;
    filter: blur(10px);
  }

	@media only screen and (max-width: 600px) {
		.center-text-large {
			font-size: 3.5rem;
		}

		.background-blur {
			filter: blur(6rem);
		}

		.starter {
			padding-right: 6rem;
			padding-bottom: 3rem;
		}

		.ender {
			padding-top: 2.5rem;
			padding-left: 10rem;
		}

		.footer-content {
			display: block;
		}
	}

	button {
		outline: none;
	}
</style>
