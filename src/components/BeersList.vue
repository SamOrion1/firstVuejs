<template>
  <body>
    <v-container fluid class="bg-surface-variant">
      <v-row> 
          <v-col justify="center" md="4" v-for="item in info" :key="item.id">
          
            <li>
              <b> {{ item.name }} </b>
              <br />
              <v-img class="bg-white" height="200" :aspect-ratio="1" :src="item.image_url"></v-img>
              <br />
              <div>{{ item.description }}</div>
              <br />
                <v-btn block depressed color="error">
                  --- Plus de details ---
                </v-btn>
              <br />
              <v-divider></v-divider>
            </li>
          </v-col>
        
      </v-row>
    </v-container>
    
    <!--<v-container>
      <v-row>
        <v-col sm="3"></v-col>
        <v-col sm="6">
          <div>
            <li :key="index" v-for="(info, index) in info">
              <b> {{ info.name }} </b>
              <br />
              <v-img :src="info.image_url"></v-img>
              <br />
              <div>{{ info.description }}</div>
              <br />
                <v-btn block depressed color="error">
                  --- Plus de details ---
                </v-btn>
              <p>___________________________________________</p>
              <br />
            </li>
          </div>
        </v-col>
        <v-col sm="3"></v-col>
      </v-row>
    </v-container> -->
  </body>
</template>



<script lang="ts">
import axios from 'axios';
import { Options, Vue } from 'vue-class-component';

@Options({
  props: {
    msg: String
  }
})

export default class BeersList extends Vue {
 
  public info: any = null;

  async mounted() {
    const result = await axios.get('https://api.punkapi.com/v2/beers');
    this.info = result.data;
    console.log(this.info)
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
</style>