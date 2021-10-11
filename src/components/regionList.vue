<template>
    <div>
        <h1>REGION LIST</h1>
        <table border='1px'>
            <tr>
                <th>Region ID</th>
                <th>Dno Region</th>
                <th>Generation mix</th>
                <th>Forcast Intensity</th>
                <th>Intensity Index</th>                
                <th>Short-name</th>
            </tr>
            <tr v-for="item in list" v-bind:key="item.id">
                <td>{{item.regionid}}</td> 
                <td>{{item.dnoregion}}</td>
                <td>{{item.generationmix[0].fuel}},{{item.generationmix[0].perc}}</td>
                <td>{{item.intensity.forecast}}</td>
                <td>{{item.intensity.index}}</td>                               
                <td>{{item.shortname}}</td>
            </tr>
        </table>
        <br/>
        <table border="1px">
            <tr>
                <th colspan="11">Generation mix</th>
            </tr>
            <tr>
                <th>Observer:</th>
                <th>1</th>
                <th>2</th>
                <th>3</th>
                <th>4</th>
                <th>5</th>
                <th>6</th>
                <th>7</th>
                <th>8</th>
                <th>9</th>
            </tr>
            <tr>
                <th>Fuel:</th>
                <th>Biomass</th>
                <th>Coal</th>
                <th>Imports</th>
                <th>Gas</th>
                <th>Nuclear</th>
                <th>Other</th>
                <th>Hydro</th>
                <th>Solar</th>
                <th>Wind</th>
            </tr>
            <tr v-for="i in list" v-bind:key="i.id">
                <td>{{i.regionid}}</td>
                <td v-for="item in i.generationmix" v-bind:key="item.id">{{item.perc}}%</td>
            </tr>
        </table>
    </div>
</template>
<script>
import Vue from 'vue';
import axios from 'axios'
import VueAxios from 'vue-axios'
Vue.use(VueAxios,axios)
export default {
    name:"regionList",
    data()
    {
        return{list:undefined, mixlist:undefined}
    },
    mounted()
    {
        Vue.axios.get('https://api.carbonintensity.org.uk/regional')
        .then((resp)=>{
            this.list=resp.data.data[0].regions;
            this.mixlist=resp.data.data[0].regions[0].generationmix;
            console.warn(resp.data.data[0].regions)
        })
    }
}  

</script>