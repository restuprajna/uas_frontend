<template>
    <div>
    

        <!-- Find Location Start here -->

        <div class="containe-fluid  py-5 primary-bg-color text-black">

        <div class="container">
            <h2 class="text-center mb-4">Find Your Location</h2>

        <div class="row mb-3 ">

            <div class="col-lg-4 col-md-4 col-sm-6 mt-5 text-center justify-content-center">

               <div class="input-group mb-3">
                    <div class="input-group-prepend">
                        <label class="input-group-text" for="inputGroupSelect01">Your Location</label>
                    </div>
                    <select class="custom-select" id="inputGroupSelect01" v-model="payment.location">
                        <option selected>Choose...</option>
                        <option >Denpasar Utara</option>
                        <option >Denpasar Selatan</option>
                        <option >Denpasar Barat</option>
                        <option >Denpasar Timur</option>
                    </select>
                    </div>
            </div>           

            <div class="col-lg-4 col-md-4 col-sm-6 mt-5 text-center">
                <form>
                    <div class="m-">
                        <input id="party" type="datetime-local" name="partydate" min="2017-06-01T08:30" max="2017-06-30T16:30" 
                       v-model="payment.date_in" required>
                        <span class="validity"></span>
                    </div>
                    
                </form>
            </div>

            <div class="col-lg-4 col-md-4 col-sm-6 mt-5 text-center">
                <form>
                    <div class="m-">
                        <input id="party" type="datetime-local" name="partydate" min="2017-06-01T08:30" max="2017-06-30T16:30" v-model="payment.date_out" required>
                        <span class="validity"></span>
                    </div>
                    
                </form>
            </div>
        </div>

        </div>


        </div>

        <!-- Find Location End here -->

        

        <!-- Billing Detail Start here -->
        <div class="container-fluid py-5 primary-bg-color text-black" id="review">
        

            
            <div class="container">
            <h2 class="text-center mb-4 ">
                Billing Detail
            </h2>
            
 
            
            </div>
                <form class="offset-lg-2 col-lg-8" @submit.prevent="addPayment">
                    <div class="mb-3">
                    <label for="nama" class="form-label">Name</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="name"
                    name="name"
                    v-model="payment.name">
                    </div>

                    <div class="mb-3">
                    <label for="email">Driver Licence (optional)</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="licence"
                    name="licence"
                    v-model="payment.licence">
                    </div>

                    <div class="mb-3">
                    <label for="email">Street</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="street"
                    name="street"
                    v-model="payment.street">
                    </div>

                    <div class="mb-3">
                    <label for="email">City</label>
                   <input type="text"
                    required
                    class="form-control"
                    id="city"
                    name="city"
                    v-model="payment.city">
                    </div>

                    <div class="mb-3">
                    <label for="email">Province</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="province"
                    name="province"
                    v-model="payment.province">
                    </div>

                    <div class="mb-3">
                    <label for="email">Regional</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="regional"
                    name="regional"
                    v-model="payment.regional">
                    </div>

                    <div class="mb-3">
                    <label for="email">Phone</label>
                    <input type="text"
                    required
                    class="form-control"
                    id="phone"
                    name="phone"
                    v-model="payment.phone">
                    </div>

                    <div class="mb-3">
                    <label for="email">Email</label>
                    <input type="email"
                    required
                    class="form-control"
                    id="email"
                    name="email"
                    v-model="payment.email">
                    </div>







                    



                    
                </form>
        
        </div>

        <!-- Billing Detail End here -->

        <!-- Additional Information Start here -->
        <div class="containe-fluid  py-5 primary-bg-color text-black">

            <div class="container">
                <h2 class="text-center mb-4">Additional Information</h2>
                <form class="offset-lg-2 col-lg-8" @submit.prevent="onSubmit">
                    

                    <div class="mb-3">
                    <label for="Review">Order Notes (optional)</label>
                    <textarea
                    class="form-control"
                    id="note"
                    name="note"
                    v-model="payment.note"
                    placeholder="Max 255 words"
                    rows="20"
                    ></textarea>
                    </div>

                    
                </form>
            </div>
        </div>


        <!-- Additional Information End here -->

        <!-- Payment Start here -->
        <div class="container py-5 primary-bg-color text-black">
            <h2 class="text-center mb-4">Payment</h2>

            <div class="position-relative">
                
                <div class="row mb-2">

                    <div class="col-8  form-check ">
                        <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1">
                        <label class="form-check-label" for="flexRadioDefault1">
                            CASH ON DELIVERY
                        </label>
                    </div>
                </div>

                <div class="row mb-2">
                    <div class="col">
                        <p class="font-italic">

                        pay with cash upon delivery
                        </p>
                    </div>
                </div>

                <div class="row mb-2">
                    <div class="form-check col-8 ">
                        <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2" checked>
                        <label class="form-check-label" for="flexRadioDefault2">
                            ONLINE PAYMENT 
                        </label>
                    </div>
                </div>

                <div class="row mb-2">
                    <div class="col-8">
                        <p class="font-italic">
                        your personal data will be used to process order, support your experience throughout this website, and for other purpose described in our privacy policy
                        </p>
                    </div>
                </div>
                
                <div class="row mb-2">
                    <div class="form-check col-8 mb-5">
                        <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
                        <label class="form-check-label" for="flexCheckDefault">
                            i have read and agree to the website terms and conditions
                        </label>

                    </div>
                </div>

                <div class="row mb-2 justify-content-center text-center">
                    <div class="col-8 ">
                       
                        <button @click.prevent="addPayment" type="submit" class="btn btn-primary w-50" style="background-color: #1687A7;">Place Order</button>
                        
                    </div>

            
                </div>

                
            </div>


        </div>

        <!-- Payment End here -->
    </div>
</template>

<script>



import axios from "axios";
export default {
    name: "Billing",
     data() {
        return {
        payment: {
            id: null,
            location: "",
            date_in: "",
            date_out: "",
            name: "",
            licence: "",
            street: "",
            city: "",
            province: "",
            regional: "",
            phone: "",
            email: "",
            note: "",
            total: "",
            status: "payment success"
        },
        };
    },
    
    methods: {
        addPayment() {
        const payment = {
            id: this.payment.id,
            location: this.payment.location,
            date_in: this.payment.date_in,
            date_out: this.payment.date_out,
            name: this.payment.name,
            licence: this.payment.licence,
            street: this.payment.street,
            city: this.payment.city,
            province: this.payment.province,
            regional: this.payment.regional,
            phone: this.payment.phone,
            email: this.payment.email,
            note: this.payment.note,
            total: this.payment.total,
            status: this.payment.status,
        };
        axios
            .post("http://localhost:8080/api/payments/add", payment)
            .then((response) => this.$router.push ("/paymentsuccess") (response))
            .catch(function (error) {
            console.log(error);
            });
        },
    },
}
</script>

<style>

</style>