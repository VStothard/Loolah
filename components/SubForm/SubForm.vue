<template>
    <div class="flex flex-row-reverse flex-wrap flex-middle container mx-auto mb-6">
        <div class="w-full sm:w-full md:w-1/2 lg:w-1/2 xl:w-1/2 text-center">
            <img src="https://source.unsplash.com/random/480x450" alt="img">
            <!-- <p>Hey {{userData.name}}</p> -->
        </div>
        <div class="w-full sm:w-full md:w-1/2 lg:w-1/2 xl:w-1/2">
            <form name="subscribe" @submit.prevent="handleSubmit" netlify-honeypot="bot-field" method="POST" netlify class="max-w-sm mx-auto">
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
                    <div class="mb-6 font-semibold">
                        <p>My cat is a rubbish conversationalist, so let's keep in touch?</p>
                    </div>
                    <div class="mb-8">
                        <div class="mb-4">
                            <input 
                                id="sub-name" name="name" type="text" placeholder="YOUR NAME" 
                                v-validate="'required|alpha_spaces'" 
                                class="border-t-0 border-l-0 border-r-0 border border-grey-darkest w-full py-4"
                            >
                            <span class="bg-black text-white text-sm ">{{ errors.first('name') }}</span>
                        </div>
                        <div class="mb-4">
                            <input 
                                id="sub-email" name="email" type="text" placeholder="YOUR EMAIL" 
                                v-validate="'required|email'" 
                                class="border-t-0 border-l-0 border-r-0 border border-grey-darkest w-full py-4"
                            >
                            <span class="bg-black text-white text-sm ">{{ errors.first('email') }}</span>
                        </div>
                    </div>
                    
                    <input 
                        class="form-button bg-black text-white p-4 border-none hover:bg-grey-darkest cursor-pointer" 
                        type="submit" 
                        value="OKAY FINE." />

                </div>
                <div v-if="step === 2">
                    <p>Thanks {{userData.name}}!</p>
                    <p>You'll hear from me soon x</p>
                </div>
            </form>
        </div>
    </div>
</template> 

<script>
import Vue from "vue";
import VeeValidate from 'vee-validate';

// import TextInput from '@/components/SubForm/parts/TextInput';


Vue.use(VeeValidate);

export default {
    components: {
        // TextInput
    },
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
            disable: false,
            testID: "identity"
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


<style scoped>
    input:focus {
        outline: none;
    }
</style>
