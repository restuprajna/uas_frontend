<template>
    <div>
        
        <h2></h2>

            <div class="container-table">
                <div class="row">
                    <div class="col-12">
                        <table class="table table-image">
                        <thead>
                            <tr>
                            <th scope="col">No</th>
                            <th scope="col">Order</th>
                            <th scope="col">Pickup Date</th>
                            <th scope="col">Return Date</th>
                            <th scope="col">Total</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(payment, index) in payments" :key="payment.id">
                            <th >{{index+1}}</th>
                            <!-- <td class="w-25">
                                <img src="../../assets/img/car-2.png" class="img-fluid img-thumbnail" alt="Car">
                            </td> -->
                            <td>{{payment.name}}</td>
                            <td>{{payment.date_in}}</td>
                            <td>{{payment.date_out}}</td>
                            
                            <td>Rp.10.000.000</td>
                            </tr>

                            <!-- <tr>
                            <th scope="row">2</th>
                            <td class="w-25">
                                <img src="../../assets/img/car-3.png" class="img-fluid img-thumbnail" alt="Car">
                            </td>
                            <td>12/12/21</td>
                            <td>21/21/21</td>
                           
                            <td>Rp.10.000.000</td>
                            </tr> -->
                        </tbody>
                        </table>   
                    </div>
                </div>
            </div>

    </div>
    
</template>

<script>
    import axios from "axios";

export default {
    name : 'Order',
    components : {

    },
    data(){
        return {
            payments: [],
        };
    },
    methods:{
        setPayments(data){
            this.payments = data;
        },
    },
    mounted(){
        axios
        .get("http://localhost:8080/api/payments")
        .then((response) => this.setPayments(response.data))
        .catch((error) => console.log(error));
    },
}
</script>

<style>

</style>