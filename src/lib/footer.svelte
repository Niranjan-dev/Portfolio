<script>
 import {Container} from 'sveltestrap'
 import {MailIcon} from 'svelte-feather-icons'
 import '../styles.css'
 import { AirplayIcon, DribbbleIcon, InstagramIcon, LinkedinIcon, GithubIcon } from 'svelte-feather-icons';
 import '../responsive.css'

 let innerWidth = 0
    // $: console.log('-->', innerWidth)
</script>

<svelte:window bind:innerWidth/>

<footer>
	{#if innerWidth > 767}
	<nav>
		<Container>
			<div class="footer-container">
                <p>© 2023 All rights reserved.</p>
			<div class="nav-list">
				<ul>
					<li><a href="https://www.linkedin.com/in/niranjan-g2k/">LinkedIn /</a></li>
					   <li><a href="https://github.com/niranjang2">Git hub /</a></li>
					   <li><a href="">Instagram</a></li>
				</ul>
			</div>
            </div>
		</Container>
	</nav>
	{:else}
	<nav>
		<Container fluid>
			<div class="footer-container">
                <p>© 2023 All rights reserved.</p>
			<div class="nav-list">
				<ul>
					<li><a href="https://www.linkedin.com/in/niranjan-g2k/"><LinkedinIcon size="20" /></a></li>
					   <li><a href="https://github.com/niranjang2"><GithubIcon size="20" /></a> </li>
					   <li><a href=""><InstagramIcon size="20" /></a></li>
				</ul>
			</div>
            </div>
		</Container>
	</nav>
	{/if}
    
</footer>