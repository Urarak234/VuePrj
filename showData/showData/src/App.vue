<template>

    <div id="mainDiv">
        <div class="list">
            <ul>
                <li v-for="nr in persons.length" 
                v-bind:key="nr" 
                v-bind:id="nr-1" 
                @click="showInfo">Person {{nr}}</li>
            </ul>
        </div>
        <div id="info" v-show="show"></div>
        
    </div>
    
</template>

<script>
export default ({
    data() {
      return {       
        persons : [
            {
                name : "Martin",
                surName : "Garix",
                age : 22,
                ocupation : "Beat-maker, Compositor, DJ",
                email : "dJ_garix@gmail.com"
            },
            {
                name : "Jhony",
                surName : "Singelton",
                age : 28,
                ocupation : "Vocalist, Street Artist",
                email : "the_three_days_grees_forever@gmail.com"
            },
            {
                name : "Lucy",
                surName : "Mc-Claren",
                age : 19,
                ocupation : "Art-creator, Designer, 2d-Game-maker",
                email : "littleMagic@gmail.com"
            },
            {
                name : "MJ",
                surName : "Brown",
                age : 26,
                ocupation : "Programmer, Freelancer",
                email : "structDC@bord.si"
            },
            {
                name : "Mike",
                surName : "Kovalski",
                age : 999,
                ocupation : "Scaring Kids",
                email : "monster_corporation@gmail.com"
            }
        ],
        show : false
      }  
    },
    methods: {

        showInfo(event){
            let leftDiv = document.getElementById("info");
            leftDiv.innerHTML = "";
            this.infoApearing();
            for (const key in this.persons) {
                if (key == event.target.id) {
                    for (const par in this.persons[key]) {
                        console.log(par," : ",this.persons[key][par]);
                        let textInfo = document.createElement("p");
                        textInfo.textContent = `${par} : ${this.persons[key][par]}`;
                        leftDiv.appendChild(textInfo);
                    }                  
                }
            }
        },
        
        infoApearing(){
            return this.show = true
        }
    },
    computed: {
    
    }
})
</script>

<style scoped>
li{
    list-style: none;
    border: 2px solid black;
    margin: 1px;
    padding: 1px;
}
li:hover{
    background-color: gray;
    color: white;
    cursor: pointer;
}
input{
    width: 100px;
}
#mainDiv{
    display: flex;
    width: inherit;
    justify-content: space-around;
    align-items: center;
    background-color: #d9dbdb;
    box-shadow: 10px 7px 20px 0px;
    border-radius: 10px;
}

#info{
    border: 3px solid salmon;
    border-radius: 30px;
    padding: 6px;
    margin-top: 20px;
    margin-bottom: 20px;
    background-color: #ffffff;
}
</style>