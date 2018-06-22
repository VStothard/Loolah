<template>
    <div class="flex container mx-auto border">
        <div class="w-1/2">
            <form name="contact" @submit.prevent="handleSubmit" netlify-honeypot="bot-field" method="post" netlify>
                <!-- div form step one -->
                <div v-if="step === 1">
                    <!--netlify hidden fields-->
                    <div>
                        <p class="hidden">     
                            <label>Don’t fill this out: <input name="bot-field"></label>   
                        </p>
                        <input type="hidden" name="form-name" value="contact" />
                    </div>
                    
                    <!-- form fields -->
                    <div>
                        <label class="uppercase" for="sub-name">Your name</label>
                        <input 
                            id="sub-name" 
                            class="border-t-0 border-l-0 border-r-0 border-b-2"
                            v-model="userData.name" 
                            v-validate="'required|alpha_spaces'" 
                            name="name" type="text">
                        <span class="bg-black text-white px-2 text-sm ">{{ errors.first('name') }}</span>
                    </div>

                    <div>
                        <label class="uppercase" for="sub-email">Your email</label>
                        <input id="sub-email" v-model="userData.email" v-validate="'required|email'" name="email" type="text">
                        <span class="bg-black text-white text-sm ">{{ errors.first('email') }}</span>
                    </div>
                    
                    <input class="form-button" type="submit" value="Send message" />
                </div>
                <div v-if="step === 2">
                    <p>Thanks {{userData.name}}! You'll hear from me soon x</p>
                </div>
            </form>
        </div>
        <div class="w-1/2">
            <img src="https://source.unsplash.com/random/200x300" alt="img">
            <p>Hi {{userData.name}}, your email is {{userData.email}}</p>
        </div>
    </div>
</template> 

<script>
import Vue from "vue";
import VeeValidate from 'vee-validate';

Vue.use(VeeValidate);

export default {
    inject: {
        $validator: "$validator"
    },
    data() {
        return {
            userData: {
                name: '',
                email: ''
            },
            step: 1,
            disable: false
        }
    },
    methods: {
        handleSubmit() {
            //validate
            this.$validator
                .validateAll()
                .then(res => {
                    if (res === true) {
                        // if all fields are completed, allow submit
                        this.disable = true;
                        this.step++;

                        console.log('submit!', this.userData.name, this.userData.email);
                        
                    }
                })
                .catch((res) => {
                    console.log("Error on submission", res);
                });
        }
    }
    
}
</script>
