<template>

    <div id="mainDiv">
        <div class="list">
            <ul>
                <li id="0" @click="showInfo">Person 1</li>
                <li id="1" @click="showInfo">Person 2</li>
                <li id="2" @click="showInfo">Person 3</li>
                <li id="3" @click="showInfo">Person 4</li>
                <li id="4" @click="showInfo">Porson 5</li>
            </ul>
        </div>
        <div id="info">

        </div>
        
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
        ]
      }  
    },
    methods: {
        showInfo(event){
            let leftDiv = document.getElementById("info");
            leftDiv.innerHTML = "";
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
        }    
    },
    computed: {
    
    }
})
</script>

<style scoped>
li{
    list-style: none;
}
input{
    width: 100px;
}
#mainDiv{
    display: flex;
    width: 100%;
    justify-content: space-around;
    align-items: center;
}
</style>
