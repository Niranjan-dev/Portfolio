<script>
	import { AirplayIcon, ArrowUpRightIcon, CodeIcon, CodesandboxIcon, CommandIcon, MailIcon } from 'svelte-feather-icons';
	import '../styles.css';
	import { Button, Container, Card, CardHeader, Row, Col, CardBody } from 'sveltestrap';
	import Carousel from 'svelte-carousel';
	import { browser } from '$app/environment';
    import '../responsive.css'
    // import { faFlag } from '@fortawesome/free-solid-svg-icons'

	let carousel; // for calling methods of the carousel instance

	const handleNextClick = () => {
		carousel.goToNext();
	};

    let innerWidth = 0
    let carouselItems = 6;
     
  $: if(innerWidth){
    if(innerWidth >= 1512){
    carouselItems = 6
    console.log('-->c', carouselItems)
  }else if(innerWidth <= 991){
    carouselItems = 4
    console.log('-->c', carouselItems)
  }else if(innerWidth <= 767){
    carouselItems = 3
    console.log('-->c', carouselItems)
  }else if(innerWidth <= 650){
    carouselItems = 2
    console.log('-->c', carouselItems)
  }else if(innerWidth <= 420){
    carouselItems = 1
    console.log('-->c', carouselItems)
  }else{
    // carouselItems = 1
  }
  }
  $: if(innerWidth <= 767){
    carouselItems = 3
  }
  $: if(innerWidth <= 650){
    carouselItems = 2
  }
  $: if(innerWidth <= 420){
    carouselItems = 1
  }

</script>

<svelte:window bind:innerWidth/>

<div>
    
	<section class="banner">
		<Container>
			<div class="banner-details">
				<div>
					<img src="../src/assets/image.png" />
					<p>Hi, I'm Niranjan</p>
					<h1>
						Building digital<br /> products, brands, and<br />experience.
					</h1>
					<Button>Latest Shots <ArrowUpRightIcon size="20" /></Button>
				</div>
			</div>
		</Container>
	</section>

    
	<section>
		<div class="carousel">
            {#if browser}
			{#if carouselItems}
            <Carousel id="carousel-container" bind:this={carousel} 
            particlesToShow={carouselItems}
            dots={false}
            autoplay={true}
            arrows={false}
            >
				<div><img id="carousel-item" src="../src/assets/A1-3.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A2-3.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A3.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A4-2.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A5-3.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A6-2.svg" /></div>
				<div><img id="carousel-item" src="../src/assets/A7-1.svg" /></div>

                
			</Carousel>
            {/if}
		{/if}

		<!-- <button on:click={handleNextClick}>Next</button> -->
        </div>
	</section>

   
    <section>
        <div class="personal-detail">
            <Container>
                <div class="personal-info">
                    <h4>Collaborate with brands and agencies to create impactful results.</h4>
                    <Row>
                        <Col lg={3}>
                            <Card>
                                <div class="card-content">
                                    <CardHeader><CodesandboxIcon/></CardHeader>
                                <CardBody>
                                    <h5>UI & UX</h5>
                                    <p>Designing interfaces that are intuitive, efficient, and enjoyable to use.</p>
                                </CardBody>
                                </div>
                              </Card>
                        </Col>
                        <Col lg={3}>
                            <Card>
                                <div class="card-content">
                                    <CardHeader><AirplayIcon/></CardHeader>
                                <CardBody>
                                    <h5>Web & Mobile App</h5>
                                    <p>Designing interfaces that are intuitive, efficient, and enjoyable to use.</p>
                                </CardBody>
                                </div>
                              </Card>
                        </Col>
                        <Col lg={3}>
                            <Card>
                                <div class="card-content">
                                    <CardHeader><CodeIcon/></CardHeader>
                                <CardBody>
                                    <h5>Design & Creative</h5>
                                    <p>Designing interfaces that are intuitive, efficient, and enjoyable to use.</p>
                                </CardBody>
                                </div>
                              </Card>
                        </Col>
                        <Col lg={3}>
                            <Card>
                                <div class="card-content">
                                    <CardHeader><CommandIcon/></CardHeader>
                                <CardBody>
                                    <h5>Development</h5>
                                    <p>Designing interfaces that are intuitive, efficient, and enjoyable to use.</p>
                                </CardBody>
                                </div>
                              </Card>
                        </Col>
                    </Row>
                </div>
            </Container>
        </div>
    </section>

    <section>
        <Container>
            <div class="project-section">
                <div>
                  <div>  <h3>Tell me about your next project</h3></div>
                <Button>Get in touch <MailIcon/></Button>
                </div>
            </div>
        </Container>
    </section>
</div>

<style>
    /* #carousel-container{
     width: 100% !important;
    position: relative !important;
    display: flex !important;
    flex-direction: column !important;
    overflow-x: hidden !important;
    }
    #carousel-item{
        display: flex !important;
    justify-content: center !important;
    flex-wrap: nowrap !important;
    } */
</style>
