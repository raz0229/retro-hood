<script>
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

<div class="footer">
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

<style>
	.footer {
		position: relative;
		background-color: #f8f8f8;
	}
	.background-blur {
		width: 100%;
		background-color: rgba(220, 20, 20, 0.85);
		height: 100vh;
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
</style>
