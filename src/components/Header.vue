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
      <div class="cart-icon"> 
        <span class="material-symbols-outlined">shopping_cart</span>
      </div>
    </div>
    
    <div class="banner">
      <div>
        <div class="banner-title">
          The first you need
        </div>
        <div class="banner-title">
          Have a cup of coffee
        </div>
        <div class="banner-btns d-flex">
          <button type="button" class="view-btn">View Menu</button>
          <button type="button" class="about-btn">About Us</button>
        </div>        
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
    transition: transform .2s ease;
  }

  .nav-btn:hover {
    transform: scale(1.1);
  }

  .header {
    display: flex;
    justify-content: space-between
  }

  .banner {
    display: flex;
    justify-content: space-between;
    margin-top: 180px;
  }

  .banner-title {
    text-align: left;
    font-size: 52px;
  }

  .banner-btns {
    gap: 2.5rem;

    button {
      border-radius: 2rem;
      width: 280px;
      height: 72px;
      background-color: $primary-color;
      color: white;
      font-weight: 700;
      font-size: 20px;
      margin-top: 20px;
      transition: 0.3s;
    }

    button:hover {
      opacity: 0.86;
    }
  
  }

  .icones {
    margin-top: 100px;
    img {
      padding-right: 25px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    img:hover {
      transform: scale(1.2);
    }
  }

  .cart-icon {
    display: flex;
    align-items: center;
    cursor: pointer;
    
    .material-symbols-outlined {
      font-variation-settings:
      'FILL' 1,
      'wght' 400,
      'GRAD' 0,
      'opsz' 24
    }

    span {
      color: $primary-color;
      padding: 5px;
      vertical-align: middle;
      transition: transform .2s ease;
    }

    span:hover {
      transform: translateY(0) scale(1.2);
    }
  }

}

</style>