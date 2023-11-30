<script>
    import { CarrouselButtonPrevious, CarrouselButtonNext, CarrouselSlide, CarrouselImageOne,  CarrouselImageTwo, CarrouselImageThree, CarrouselText } from '$lib/index.js'
  
  </script>


<carrousel>
  <!-- <CarrouselSlide> -->
    <section class="carrousel">
      <h2>Stay up to date</h2>
    <CarrouselText>
    <CarrouselImageOne />
    </CarrouselText>
  
    
    <CarrouselText>
    <CarrouselImageTwo />
    </CarrouselText>
   

    <CarrouselText>
    <CarrouselImageThree />
    </CarrouselText>

    <CarrouselText>
    <CarrouselImageOne />
    </CarrouselText>

    <CarrouselButtonPrevious />
    <CarrouselButtonNext />

    <!-- </CarrouselSlide> -->
  </section>
</carrousel>
  
  
<style>
    

  .carrousel {
  width: 100%;
  height: 93vw;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  background-image: url(/assets/bg-shape.svg);
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  padding: 0;
  overflow-x: hidden;
 }

 h2 {
  font-family: var(--paragraph-font);
  font-weight: 200;
  line-height: 0.9em;
  text-align: center;
  font-size: clamp(24px, 3.8vw, 50px);
 }

 section {
  display: flex;
  flex-direction: row;
  padding: 0 0 0 4rem;
  overflow: auto;
  width: 100%;
  margin: 4% 0 2% 0;
  transition: 0.2s ease-in;
  scroll-snap-type: x mandatory;
 }


</style> 