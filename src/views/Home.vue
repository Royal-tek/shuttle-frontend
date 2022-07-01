<template>
  <div class="home">
    <Navbar/>
    <div class="banner py-2 mt-3 mb-2">
      <div class="container" style="height:100%">
        <div class="row" style="height: 100%;">
          <div class="col-md-6 text-part">
            <h1 class="text-dark text-center text-uppercase py-3" style="font-weight:500;">order your shuttle now</h1>
            <router-link to="/booking" style="text-decoration:none; width: 100%;" class="text-dark"><input type="submit" value="Book Now" class="btn  ride-btn py-3"></router-link>
          </div>
          <div class="col-md-6 img-part">
            <img src="../assets/bus.jpg" class="img-fluid" alt="">
          </div>

        </div>
      </div>
    </div>

    <div class="nextBanner my-2 py-2">
      <div class="container">
        <div class="row">
          <div class="col-md-6 my-3">
            <h3 class="text-center py-2"><i class="fa fa-bus"></i> Book at your convenience</h3>
            <p class="text-center">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint suscipit debitis minus asperiores facere accusantium nisi, iusto, impedit eaque, veritatis deserunt? Quasi nobis perferendis ut placeat, minima ipsa pariatur deleniti.</p>
          </div>
          <div class="col-md-6 my-3">
            <h3 class="text-center py-2"><i class="fa fa-clock"></i> Go anywhere in good time</h3>
            <p class="text-center">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolorem mollitia rerum est quidem iusto magnam nemo doloribus tempore maiores voluptatibus. Ea minima ut eveniet necessitatibus placeat ad voluptatibus doloremque et.</p>
            </div>
            <div class="col-md-6 my-3">
            <h3 class="text-center py-2"><i class="fa fa-user"></i> 24/7 Availability</h3>
            <p class="text-center">Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint suscipit debitis minus asperiores facere accusantium nisi, iusto, impedit eaque, veritatis deserunt? Quasi nobis perferendis ut placeat, minima ipsa pariatur deleniti.</p>
          </div>
          <div class="col-md-6 my-3">
            <h3 class="text-center py-2"><i class="fa fa-money"></i> Affordable prices</h3>
            <p class="text-center">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolorem mollitia rerum est quidem iusto magnam nemo doloribus tempore maiores voluptatibus. Ea minima ut eveniet necessitatibus placeat ad voluptatibus doloremque et.</p>
            </div>
        </div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Navbar from '../components/Navbar.vue';
import Footer from '../components/Footer.vue'
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
    Navbar, Footer
}
}
</script>

<style lang="scss" scoped>
.banner{
  width: 100%;
  // height: 50vh;
  // background: url(../assets/2.jpg);
  background-position: center;
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: cover;
}
.text-part{
  display: flex;
  // align-items: center;
  justify-content: center;
  flex-direction: column;

  h1{
    font-size: 65px;
  }
  .ride-btn{
    width: 100%;
    color: #fff;
    background-color: rgb(82, 176, 104);
  }
}
@media (max-width:900px){
.text-part{
  h1{
    font-size: 60px;
  }
}
}
@media (max-width:780px){
.text-part{
  h1{
    font-size: 60px;
    margin: 3px 0 0;
  }
}
}
.img-part{
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
