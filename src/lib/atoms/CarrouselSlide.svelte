
<article class="carrousel-item" aria-hidden="false">
    <div class="carrousel-item-image">
        <img src="/assets/image 253.png" alt="children playing">
    </div>
    <h3>Iaculis nulla a nam pharetra augue congue.</h3>
</article>

<style>


.carrousel-item {
  background-image: url(/assets/item-bg-shape.svg);
  background-repeat: no-repeat;
  background-size: contain;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 2rem;
  width: clamp(200px, 28%, 28%);
  height: clamp(250px, 31vw, 31vw);
  flex: 0 0 auto;
  overflow: hidden;
  padding: clamp(0.5rem, 1vw, 1vw);
  margin-right: 16px;
  box-sizing: border-box;
  scroll-snap-align: start;
}

.carrousel-item > h3 {
  font-size: clamp(16px, 1.5vw, 24px);
  font-weight: 400;
  font-family: var(--paragraph-font);
  color: var(--charcoal);
  padding: clamp(0.5rem, 1vw, 1vw);
}

.carrousel-item-image {
  width: 100%;
  height: 60%;
  overflow: hidden;
  border-radius: 5px;
}

.carrousel-item .carrousel-item-image > img {
  border-radius: 5px;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top;
}

</style>