<script>
	import { Button, Col, Row, Container } from 'sveltestrap';
	import { onMount } from 'svelte';
	import '../styles.css';
	import { AirplayIcon, DribbbleIcon, InstagramIcon, LinkedinIcon, MailIcon, GithubIcon } from 'svelte-feather-icons';
	import '../responsive.css'
	
	let innerWidth = 0
    // $: console.log('-->', innerWidth)
</script>


<svelte:window bind:innerWidth/>

<header>
	{#if innerWidth > 767}
	<nav>
	   <Container>
		   <div class="nav-container">
			   <a href="mailto:niranjan.g2k@gmail.com" target="_blank">
				   <span><MailIcon size="20" /></span>
				   <span>Get in touch</span>
			   </a>
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
		   <div class="nav-container">
			   <a href="" target="_blank">
				   <span><MailIcon size="20" /></span>
				   <span>Get in touch</span>
			   </a>
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
</header>


<style>
</style>
