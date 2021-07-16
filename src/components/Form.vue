<template>
    <div>
        <pre>
            {{JSON.stringify(formValues, null, 2)}}
        </pre>
    </div>
    <form @submit.prevent="submitForm">
    <div>
        <label for="name">Name</label>
        <!-- trim is modifier prevents white spaces in input field  -->
        <input type="text" name="name" placeholder="Enter your name" v-model.trim="formValues.name">  
    </div>
    <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
            <option value="">Select a country</option>
            <option value="Nepal">Nepal</option>
            <option value="England">England</option>
            <option value="Mandives">Maldives</option>
        </select>
    </div>
    <div>
        <label for="joblocation">Job Location</label>
        <select id="joblocation" multiple v-model="formValues.jobLocation">
            <option value="Nepal">Nepal</option>
            <option value="England">England</option>
            <option value="Mandives">Maldives</option>
        </select>
    </div>
    <div>
        <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no"/>
        <label for="remoteWork">Open to remote work?</label>
    </div>
    <br />
    <div>
        <label for="">Skill Set</label>  <br />
        <input type="checkbox" id="html" value="html" v-model="formValues.skillSet"/>
        <label for="html">Html</label>
        <input type="checkbox" id="css" value="css" v-model="formValues.skillSet"/>
        <label for="css">css</label>
        <input type="checkbox" id="react" value="react" v-model="formValues.skillSet"/>
        <label for="react">React</label>
        <input type="checkbox" id="jscript" value="jscript" v-model="formValues.skillSet"/>
        <label for="jscript">jscript</label>
    </div>
    <div>
        <label for="">Years of experience</label>
        <input type="radio" id="exp1" value="0-2" v-model="formValues.experience"/>
        <label for="">0-2  years</label>
        <input type="radio" id="exp2" value="3-5" v-model="formValues.experience"/>
        <label for="">3-5 years</label>
        <input type="radio" id="exp3" value="6-10" v-model="formValues.experience"/>
        <label for="">6-10 years</label>
    </div>
    <div>
        <label for="age">Age</label>
        <input @keyup.enter="submitForm" type="number" id="age" v-model="formValues.age">
    </div>
    <div>
        <button>Submit</button>
    </div>
    </form>
</template>

<script>
export default {
    name: 'form',
    data() {
        return{
            formValues:{
                name:'',
                country:'',
                jobLocation:[],
                remoteWork: false,
                skillSet:[],
                experience:'',
                age: null
            },
            
        };
    },
    methods:{
        submitForm(){
            console.log('Form values', this.formValues)
        }
    }
}
</script>

<style>
#form{
       font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>