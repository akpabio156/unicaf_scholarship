<template>
  <div>
    <RegModal v-if="showModal" />
  </div>
  <div class="container-fluid">
    <img src="@/assets/black.smile.png" alt="" />

    <div class="form_div container">
      <div class="headText">
        <h3>Register For A Scolarship</h3>
        <p>fill the form below and one of our adviser will contact you soon.</p>
      </div>

      <form @submit.prevent="registerForm">
        <div class="form_details">
          <div class="">
            <input
              type="text"
              v-model="regDetails.first_name"
              name="first_name"
              id="first_name"
              required
              placeholder="First Name"
            />
            <br /><br />
            <input
              type="email"
              v-model="regDetails.email"
              name="email"
              id="email"
              required
              placeholder="E-mail"
            />
            <br /><br />
            <input
              type="number"
              v-model="regDetails.phone_number"
              name="phone_number"
              id="phone_number"
              required
              placeholder="+234"
            />
          </div>
          <div class="">
            <input
              type="text"
              v-model="regDetails.last_name"
              name="last_name"
              id="last_name"
              required
              placeholder="Last Name"
            />
            <br /><br />
            <input
              type="text"
              v-model="regDetails.password"
              name="password"
              id="password"
              required
              placeholder="country"
            />
            <br /><br />
            <input
              type="text"
              v-model="regDetails.country"
              name="country"
              id="country"
              required
              placeholder="password"
            />
          </div>
        </div>
        <input type="submit" class="submit-btn btn btn-block text-white mt-3" />
      </form>
    </div>
  </div>
</template>

<script>
import RegModal from "@/components/RegModal.vue";
import axios from "axios";
export default {
  components: { RegModal },
  data() {
    return {
      showModal: false,
      regDetails: {
        last_name: "",
        first_name: "",
        phone_number: "",
        email: "",
        password: "",
        country: "",
      },

      // showModal: false,
    };
  },
  methods: {
    async registerForm() {
      // let res2 = await axios.get(
      //   "https://authenticatapi.herokuapp.com/api/register"
      // );
      // console.log(res2);
      console.log(this.regDetails);
      let res = await axios.post(
        "https://authenticatapi.herokuapp.com/api/register",
        this.regDetails
      );
      if (res.data.status === "success") {
        this.showModal = true;
        setTimeout(() => {
          this.regDetails.first_name = "";
          this.regDetails.last_name = "";
          this.regDetails.email = "";
          this.regDetails.phone_number = "";
          this.regDetails.password = "";
          this.regDetails.country = "";
          this.showModal = false;
        }, 2000);
      }

      console.log(res);
    },
    // async registerForm() {
    //   console.log(this.regDetails);
    //   await axios
    //     .post(
    //       "https://authenticatapi.herokuapp.com/api/register",
    //       this.regDetails
    //     )
    //     .then((response) => console.log(response))
    //     .catch((err) => console.log(err.message));
    // },
  },
};
</script>

<style scoped>
.container-fluid img {
  height: 70vh;
  width: 100%;
}
.container-fluid {
  background-color: grey;
  height: 82.8vh;
}
/* form */
.form_div {
  position: relative;
  height: 40vh;
  width: 33%;
  border: 1px solid rgb(224, 222, 222);
  bottom: 20rem;
  right: 15rem;
  background: rgb(240, 237, 237);
  border-radius: 3px;
  /* z-index: -1; */
}

.headText {
  text-align: center;
  padding: 5px;
}
.form_details {
  display: flex;
  justify-content: space-between;
  /* gap: 20px; */
}
.form_div input {
  border-radius: 5px;

  border: 1px solid grey;
}
input {
  width: 100%;
  padding: 3px;
}
.btn {
  background: rgb(255, 126, 150);
  color: white;
  width: 100%;

  margin-top: 20px;
}

/* Resposiveness */
@media (max-width: 1440px) {
  input {
    width: 100%;
  }
  .btn {
    background: rgb(255, 126, 150);
    color: white;
    width: 100%;
  }
}

@media (max-width: 1243px) {
  .container-fluid {
    height: 84vh;
  }
  .form_div {
    position: relative;
    height: 40vh;
  }
  input {
    width: 90%;
  }
  .btn {
    background: rgb(255, 126, 150);
    color: white;
    width: 95%;
  }
  .headText h3 {
    font-size: 20px;
  }
  .headText p {
    font-size: 12px;
  }
}
@media (max-width: 1199px) {
  .form_div {
    position: relative;
    height: 47vh;
    width: 33%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 20rem;
    right: 15rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .container-fluid {
    height: 84 vh;
  }
  .form_div {
    position: relative;
    height: 40vh;
  }
  input {
    width: 90%;
  }
  .btn {
    background: rgb(255, 126, 150);
    color: white;
    width: 95%;
  }
  .headText h3 {
    font-size: 20px;
  }
  .headText p {
    font-size: 12px;
  }
}
@media (max-width: 1243px) {
  .form_div {
    position: relative;
    height: 43vh;
  }
}
@media (max-width: 1024px) {
  .form_div {
    position: relative;
    height: 40vh;
    width: 36%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 20rem;
    right: 12rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .headText {
    text-align: center;
    padding: 5px;
  }
  .headText h3 {
    font-size: 20px;
  }
  .headText p {
    font-size: 11px;
  }
  input {
    width: 90%;
  }
}
@media (max-width: 903px) {
  .form_div {
    position: relative;
    height: 43vh;
    width: 39%;
  }
}
@media (max-width: 768px) {
  .form_div {
    position: relative;
    height: 43vh;
    width: 45%;
  }
}
@media (max-width: 681px) {
  .form_div {
    position: relative;
    height: 42vh;
    width: 62%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 7.7rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}
@media (max-width: 651px) {
  .form_div {
    right: 10.5rem;
    bottom: 15rem;
  }
}
@media (max-width: 643px) {
  .form_div {
    position: relative;
    height: 42vh;
    width: 60%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 7.5rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}
@media (max-width: 615px) {
  .form_div {
    position: relative;
    height: 42vh;
    width: 62%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 7rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}
@media (max-width: 605px) {
  .form_div {
    position: relative;
    height: 42vh;
    width: 62%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 6.7rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}
@media (max-width: 531px) {
  .form_div {
    position: relative;
    height: 45vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 5rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}

@media (max-width: 500px) {
  .form_div {
    position: relative;
    height: 45vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 5rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
}
@media (max-width: 425px) {
  .form_div {
    position: relative;
    height: 45vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 15rem;
    right: 4rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  @media (max-width: 414px) {
    .form_div {
      position: relative;
      height: 35vh;
      width: 65%;
      border: 1px solid rgb(224, 222, 222);
      bottom: 20rem;
      right: 4rem;
      background: rgb(240, 237, 237);
      border-radius: 3px;
    }
    .container-fluid {
      height: 68vh;
    }
    .container-fluid img {
      height: 65vh;
    }
  }
  .headText h3 {
    font-size: 15px;
    padding: 10px;
  }
  .headText p {
    font-size: 10px;
  }
  input {
    font-size: 14px;
  }
}
@media (max-width: 393px) {
  .form_div {
    position: relative;
    height: 38vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 17rem;
    right: 3.6rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .container-fluid {
    height: 72vh;
  }
  .container-fluid img {
    height: 63vh;
  }
}

@media (max-width: 390px) {
  .form_div {
    position: relative;
    height: 38vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 17rem;
    right: 3.6rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .container-fluid {
    height: 72vh;
  }
  .container-fluid img {
    height: 63vh;
  }
}
@media (max-width: 375px) {
  .form_div {
    position: relative;
    height: 45vh;
    width: 65%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 20rem;
    right: 3.6rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .container-fluid {
    height: 81.2vh;
  }
  .container-fluid img {
    height: 74vh;
  }
}
@media (max-width: 320px) {
  .form_div {
    position: relative;
    height: 45vh;
    width: 76%;
    border: 1px solid rgb(224, 222, 222);
    bottom: 18rem;
    right: 2rem;
    background: rgb(240, 237, 237);
    border-radius: 3px;
  }
  .container-fluid {
    height: 81.2vh;
  }
  .container-fluid img {
    height: 74vh;
  }
}
</style>
