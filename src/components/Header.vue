<template>
  <section id="header">
    <div class="header">
      <div>
        <img src="logo.png" alt=""/>
      </div>
      <div class="d-flex center">
        <button type="button" class="btn btn-link nav-btn">Home</button>
        <button type="button" class="btn btn-link nav-btn">Coffee Menu</button>
        <button type="button" class="btn btn-link nav-btn">About us</button>     
      </div>
      <div></div>
    </div>
    
    <div class="banner">
      <div>
        <div class="banner-title">
          The first you need
        </div>
        <div class="banner-title">
          Have a cup of coffee
        </div>
        <button type="button" class="view-btn">View Menu</button>
        <div class="icones">
          <img src="./../assets/icon-1.png" />
          <img src="./../assets/icon-2.png" />
          <img src="./../assets/icon-3.png" />
          <img src="./../assets/icon-4.png" style="margin-bottom: 15px;"/>
        </div>
      </div>
      <div>
        <img src="./../assets/banner.png" />
      </div>
      
    </div>
  </section>
</template>

<script>

</script>

<style lang="scss" scoped>
@import './../sass/tokens';

#header {
  padding: 15px 250px 0 250px;

  .center {
    align-items: center;
    align-content: center;
  }

  .nav-btn {
    color: $primary-color;
    font-weight: 700;
    text-decoration: none;
  }

  .nav-btn:hover {
    transform: scale(1.1);
  }

  .header {
    display: flex;
    justify-content: space-between
  }

  .banner {
    display: grid;
    grid-template-columns: auto auto;
    margin-top: 180px;
  }

  .banner-title {
    text-align: left;
    font-size: 52px;
  }

  .view-btn {
    width: 469px;
    height: 78px;
    background-color: $primary-color;
    color: white;
    font-weight: 700;
    font-size: 24px;
    border-radius: 40px;
    margin-top: 20px;
    transition: 0.3s;
  }

  .view-btn:hover {
    opacity: 0.8;
  }

  .icones {
    margin-top: 100px;
    img {
      padding-right: 25px;
      cursor: pointer;
    }
  }

}

</style>