<template>
    <div>
        <vue-funnel-graph :width="width" :height="height" :labels="labels"
            :values="values" :colors="colors" :sub-labels="subLabels" :direction="direction"
            :gradient-direction="gradientDirection"
            :animated="true" :display-percentage="true">   
        </vue-funnel-graph>
    </div>
</template>

<script>
import { VueFunnelGraph } from 'vue-funnel-graph-js'

export default {
    name: 'Funil',
    components: {
      VueFunnelGraph
  },
  data() {
      return {
          labels: ['Usuários Cadastrados', 'Analisando Perfil', 'Usuários com Match'],
          subLabels: ['Direct', 'Social Media', 'Ads'],
          values: [
          // with the given Labels and SubLabels here's what the values represent:
          // 
          // Direct, Social, Ads  
          //    |      |     |  
          //    v      v     v
              [3000, 2500, 6500], // Segments of "Impressions" from top to bottom
              [3000, 1700, 1000], // Segments of "Add To Cart"
              [600,  200,  130]   // Segments of "Buy"
          ],
          colors: [
              ['#FFB178', '#FF3C8E'], // color set for "Impressions" segment
              ['#A0BBFF', '#EC77FF'], // color set for "Add To Cart" segment
              ['#A0F9FF', '#7795FF']  // color set for "Buy" segment
          ],
          direction: 'vertical',
          gradientDirection: 'vertical',
          height: 500,
          width: 400
      };
  }
}
</script>