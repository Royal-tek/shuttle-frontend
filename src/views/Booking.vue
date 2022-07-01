<template>
    <div class="holder">
        <Navbar/>
        <div class="banner py-2 my-2">
            <div class="container">
                <div class="number mb-2">1</div>
                <p class="text-center py-2">Select Journey</p>
                <div class="row">
                    

                    <div class="col-md-6 my-3">
                        <!-- {{from}} -->
                        <div class="box-from">
                            <form class="form">
                                <div class="input-group">
                                    <select class="form-select shadow-none py-3" v-model="from">
                                        <option value="">FROM  <i class="fa fa-caret"></i> </option>
                                        <option value="ncb">New College Building </option>
                                        <option value="ocb">Old College Building </option>
                                        <option value="ah">Abraham Hall </option>
                                        <option value="ih">Isaac Hall </option>
                                        <option value="dh">Daniel Hall </option>
                                        <option value="jh">Joseph Hall </option>
                                        <option value="dorcas">Dorcas Hall </option>
                                        <option value="abigail">Abigail Hall </option>
                                        <option value="sarah">Sarah Hall </option>
                                        <option value="engbld">Engineering Building </option>
                                        <option value="libary">Libary </option>
                                        <option value="cafe">Cafeteria </option>
                                        <option value="field">Field </option>
                                        <option value="senate">Senate Building </option>
                                        <option value="pq">Professors Quarters </option>
                                        <option value="sq">Staff Quarters </option>
                                        <option value="gate">Gate </option>
                                    </select>
                                </div>
                            </form>
                        </div>
                    </div>
                    <div class="col-md-6 my-3">
                        <div class="box-to">
                            <form class="form">
                                <div class="input-group">
                                    <select class="form-select shadow-none py-3" v-model="to">
                                        <option value="">TO  </option>
                                        <option value="ncb">New College Building </option>
                                        <option value="ocb">Old College Building </option>
                                        <option value="ah">Abraham Hall </option>
                                        <option value="ih">Isaac Hall </option>
                                        <option value="dh">Daniel Hall </option>
                                        <option value="jh">Joseph Hall </option>
                                        <option value="dorcas">Dorcas Hall </option>
                                        <option value="abigail">Abigail Hall </option>
                                        <option value="sarah">Sarah Hall </option>
                                        <option value="engbld">Engineering Building </option>
                                        <option value="libary">Libary </option>
                                        <option value="cafe">Cafeteria </option>
                                        <option value="field">Field </option>
                                        <option value="senate">Senate Building </option>
                                        <option value="pq">Professors Quarters </option>
                                        <option value="sq">Staff Quarters </option>
                                        <option value="gate">Gate </option>
                                    </select>
                                </div>
                            </form>
                        </div>
                    </div>

                    <div class="col-md-3 my-2  book-btn">
                        <input type="submit" class="btn py-3" value="Next" @click="setJourney()">
                    </div>
                </div>
                
            </div>
        </div>
        
        <div class="banner2 py-3 my-3" v-if="step1 == true">
            <div class="container">
                <div class="number mb-2">2</div>
                <p class="text-center py-2">Select Driver</p>
                <div class="row">
                    <div class="col-md-4 my-3" v-for="driver in drivers" 
                    :key="driver.id"
                    @click="selectedId = driver.id, step2=true"

                    >
                        <div class="driver-box" :class="selectedId == driver.id ? 'driver-active' : null">
                            <div class="top-part">
                                <p>{{driver.name}}</p>
                                <img src="../assets/1.jpg" class="img-fluid mb-3" alt="">
                            </div>
                            <div class="middle-part">
                            <p>Plate No :</p>
                            <p> {{driver.plate_no}}</p>
                            
                            </div><hr>
                            <div class="bottom-part">
                                
                                <i class="fa fa-star"></i>
                                <i class="fa fa-star"></i>
                                <i class="fa fa-star"></i>
                                <i class="fa fa-star"></i>
                                <i class="fa fa-star"></i>
                            </div>
                        </div>
                    </div>
                
                </div>
            </div>
        </div>
    
        <div class="banner3 py-3 my-3" v-if="step2 == true">
            <div class="container">
                
                <div class="number mb-2">3</div>
                <p class="text-center py-2">Confirm Ride</p>
                <form class="form">
                    <div class="input-group my-3">
                        <textarea cols="30" rows="10" class="form-control shadow-none" style="border-color:rgb(82, 176, 104)" :placeholder='`Enter Description \n Eg: I am wearing a black trouser and white shirt\n Eg: I am under the tree beside the bank`'></textarea>
                    </div>
                    <div class="input-group my-3">
                        <input type="submit" class="btn btn-success py-3 " value="Book Ride" style="background-color: rgb(82, 176, 104); width:100%; color: white;">
                    </div>
                </form>
            </div>
        </div>
        <Footer/>
    </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
export default {
    name : 'Booking',
    components:{
        Navbar, Footer
    },
    data(){
        return{
            step1 : false,
            step2 : false,
            from : '',
            to : '',
            selectedId: '',
            drivers: [
                {
                    id: 123,
                    name : 'Afonime Royal',
                    plate_no : 'kjdumdkms'
                },
                {
                    id: 124,
                    name : 'Oyebode Rejoice',
                    plate_no : 'hbwebwewe'
                },
                {
                    id: 125,
                    name : 'Adesina Ruth',
                    plate_no : 'nnishdkd'
                }
            ]
        }
    },
    methods:{
        setJourney(){
            // alert('hello world')
            if(this.to == '' && this.from == ''){
                alert('Select Journey')
            }else if(this.to == '' && this.from != '' || this.to != '' && this.from == ''){
                alert('Journey path not complete')
            }
            else if(this.to == this.from){
                alert("You cannot go to location where you already at")
            }
            else if(this.to != '' && this.from != ''){
                this.step1=true
            }
        },
    }
}
</script>

<style lang="scss" scoped>
.book-btn{
    margin: 0 auto;
    width: 100%;

    input{
        background-color: rgb(82, 176, 104);
        width: 100%;
        color: #fff;
    }
    
}
.number{
    text-align: center;
    background-color: rgb(82, 176, 104);
    width: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 60px;
    margin: 0 auto;
    color: #fff;
    font-weight: bold;
    border-radius: 50%;
    font-size: 20px;
}
.driver-box{
    border: 1px solid rgb(82, 176, 104);
    padding: 30px;
    border-radius: 30px;
    cursor: pointer;
    transition: all ease-in-out .5s;

    &:hover{
        
        background-color: rgb(82, 176, 104);
        color: #fff;

        i{
            color: #fff;
        }
    }
    &:focus{
        background-color: blue;
    }
}
.bottom-part{
    display: flex;
    align-items: center;
    justify-content: center;

    i{
        color: rgb(82, 176, 104);
        font-size: 20px;
        margin: 0 15px;
    }
}
.top-part{
    display: flex;
    justify-content: space-between;

    img{
        max-width: 50px;
        max-height: 50px;
        border-radius: 50%;


    }
}
.middle-part{
    display: flex;
    align-items: center;
    justify-content: space-between;
}

.driver-active {
    border: 3px solid green;
}
</style>