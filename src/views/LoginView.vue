<template>
    <section class="">
  <div class="container py-5 h-100">
    <div class="row d-flex align-items-center justify-content-center h-100">
      <div class="col-md-8 col-lg-7 col-xl-6">
        <img src="https://i.postimg.cc/sx8k4CF5/5843873-1.jpg"
          class="img-fluid" alt="Phone image">
      </div>
      <div class="col-md-7 col-lg-5 col-xl-5 offset-xl-1">
        <form>
          <!-- Email input -->
          <div class="form-outline mb-4">
            <input type="email" id="form1Example13" class="form-control form-control-lg" />
            <label class="form-label" for="form1Example13">Email address</label>
          </div>

          <!-- Password input -->
          <div class="form-outline mb-4">
            <input type="password" id="form1Example23" class="form-control form-control-lg" />
            <label class="form-label" for="form1Example23">Password</label>
          </div>

          

          <!-- Submit button -->
          <button type="submit" class="btn btn-primary btn-lg btn-block">Sign in</button>

        

          


        </form>
      </div>
    </div>
  </div>
</section>
</template>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Cinzel&display=swap");

label {
    color: rgb(255, 255, 255);
    font-family: "Cinzel", serif;

}

.btn {
    color: white;
    background-color: black;
    border: 1px solid white;
    font-family: "Cinzel", serif;

}

.btn:hover {
transition: 0.3s ;
transform: scaleX(1.0);
box-shadow: 0 0 4px white;
background-color: white;
color: black;
}

@media only screen and (max-width:300px){
 form {
    height: 15.67rem !important;
 }   

 .img-fluid {
   width: 20rem!important;
   height: 14rem;
   margin-top: 0;
   padding: 0;
 }
}
</style>