<template>
  <div>
    <client-only placeholder="loading...">
      <d3-network :net-nodes="nodes" :net-links="links" :options="options" />
    </client-only>
  </div>
</template>

<script>
import D3Network from 'vue-d3-network'
import rawArticles from '~/assets/icons/science-book-svgrepo-com.svg?raw'
import rawDna from '~/assets/icons/dna-svgrepo-com.svg?raw'
import rawRat from '~/assets/icons/rat-svgrepo-com.svg?raw'
import rawComputer from '~/assets/icons/monitor-with-stats-svgrepo-com.svg?raw'

export default {
  name: 'KnowledgeLinks',
  components: {
    D3Network
  },
  data() {
    return {
      nodes: [
        {
          id: 1,
          name: 'Target Safety Assessment',
          svgSym: rawDna
        },
        {
          id: 2,
          name: 'What literature is related to my target?',
          svgSym: rawArticles
        },
        {
          id: 3,
          name: 'What animal study data do we have for this target?',
          svgSym: rawRat
        },
        {
          id: 4,
          name: 'What clinical data do we have for this target?',
          svgSym: rawComputer
        }
      ],
      links: [
        {
          tid: 1,
          sid: 2
        },
        {
          tid: 1,
          sid: 3
        },
        {
          tid: 1,
          sid: 4
        }
      ],
      options: {
        nodeSize: 80,
        force: 20000,
        nodeLabels: true,
        fontSize: 16
      }
    }
  }
}
</script>
<style src="vue-d3-network/dist/vue-d3-network.css"></style>
<style scoped></style>
