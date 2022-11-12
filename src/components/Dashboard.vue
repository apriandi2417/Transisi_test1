<template>
  <div class="dashboard">
    <div class="container p-0">
      <!-- breadcrumb -->
      <div class="row mb-5 p-3 rounded" style="background-color: rgb(19, 19, 19);">
        <div class="col-md-6 text-white justify-content-center" style="padding: 150px; text-align: left;">
          <h3><strong>Hi Samantha</strong></h3>
          <p>Lorem ipsum dolor sit elit. Id, quidem!</p>
          <div class="search">
            <i class="fa fa-search"></i>
            <input type="text" class="form-control" placeholder="Search Task or Project...">
          </div>
          <br>
          <br>
          <br>
          <h6>Projects <span>(13)</span></h6>
          <div class="row justify-content-center" style="text-align: center;">
            <div class="col-md-4 rounded mb-3" v-for="item in icons">
              <button type="button" class="btn btn-success p-4">
                {{ item.sk }}
              </button>
              <p class="mt-2"><small>{{ item.name }}</small></p>
            </div>
            <div class="col-md-4 rounded" >
              <button type="button" class="btn btn-success p-4">
                8+
              </button>
            </div>
          </div>
        </div>
        <div class="col-md-6 bg-white rounded position-relative" style="padding: 60px; text-align: left;">
          <div>
            <h3><strong>Cyber Punk</strong></h3>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. At officiis deleniti explicabo cupiditate ratione iusto corrupti veniam id illum omnis.</p>
          </div>
          <div>
            <h5>Today</h5>
            <hr>
            <div class="row" v-for="item in product">
              <div class="col-md-8">
                <!-- <form> -->
                  <div class="form-check">
                    <input type="checkbox" class="form-check-input" id="exampleCheck1">
                    <label class="form-check-label" for="exampleCheck1">{{ item.judul }}</label>
                  </div>
                <!-- </form> -->
              </div>
              <div class="col-md-4 pb-2">
                <button type="button" class="btn btn-outline-success btn-sm w-100" v-if="item.status == 1">Approved</button>
                <button type="button" class="btn btn-outline-primary btn-sm w-100" v-if="item.status == 2">In Progress</button>
                <button type="button" class="btn btn-outline-warning btn-sm w-100" v-if="item.status == 3">In Review</button>
                <button type="button" class="btn btn-outline-secondary btn-sm w-100" v-if="item.status == 4">Waiting</button>
              </div>
            </div>
            <div class="position-absolute bottom-0 end-0">
                <button type="button" class="btn btn-success m-3" @click.prevent="add()">+</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import axios from "axios";

export default {
  name: "Dashboard",
  components: {
  },
  data() {
    return {
      product: [
        {
          // id : 1, 
          judul: "Create initial layout for homepage", 
          status: 1, 
          ischeklist: 1
        },
        {
          // id : 2, 
          judul: "Fixing icons with transparant background", 
          status: 2, 
          ischeklist: 1
        },
        {
          // id : 3, 
          judul: "Fixing icons with transparant background", 
          status: 2, 
          ischeklist: 1
        },
        {
          // id : 4, 
          judul: "Create initial layout for homepage", 
          status: 2, 
          ischeklist: 1
        },
        {
          // id : 5, 
          judul: "Discussions regarding workflow improvement", 
          status: 3, 
          ischeklist: 0
        },
        {
          // id : 6, 
          judul: "Create quotation for app redesign project", 
          status: 4, 
          ischeklist: 0
        },
      ],
      icons: [
        {
          name: "Green House",
          sk:"GH"
        },
        {
          name: "Cyber Punk",
          sk:"CP"
        },
        {
          name: "Easy Crypto",
          sk:"EC"
        },
        {
          name: "Travel App",
          sk:"TA"
        },
        {
          name: "Landing Page",
          sk:"LP"
        },
      ],
    };
  },
  methods: {
    add(){
      let id = Math.floor(Math.random() * (this.product.length)) //randomly generated id
      let judul = this.product[id].judul;
      this.product.push({judul:judul, status:4})
      // console.log(judul);
    }
  },
  mounted() {

  },
};
</script>

<style>
      .search{
       position: relative;
       box-shadow: 0 0 40px rgba(51, 51, 51, .1);
       }

       .search input{

        height: 60px;
        text-indent: 25px;
        border: 2px solid #d6d4d4;
        border-radius: 30px;
        opacity: 0.5;
       }


       .search input:focus{

        box-shadow: none;
        border: 2px solid blue;


       }

       .search .fa-search{

        position: absolute;
        top: 20px;
        left: 16px;

       }
</style>