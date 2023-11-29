<script>
    import { CarrouselButton, CarrouselSlide, CarrouselNavigatie } from '$lib/index.js'
  
  </script>

<header>
    <CarrouselButton />
  
    <CarrouselSlide />
  
    <!-- <CarrouselImages/> -->

    <CarrouselNavigatie/>
  </header>
  
  
  <style>
    header {
      display: flex;
      flex-flow: row nowrap;
      justify-content: flex-start;
      align-items: center;
      gap:1rem;
    }
  </style>