<template>
    <PowerBIReportEmbed 
    :embedConfig="{
      type: 'report',
      id: reportId,
      embedUrl: embedUrl,
      accessToken: token,
      tokenType: 1,
      permissions: 7, 
      viewMode: 1,
      settings: {
        panes: {
          filters: {
            expanded: false,
            visible: false
          }
        },
        background: 1,
      }
    }"
    class="powerbi"
    :phasedEmbedding =  false
    :eventHandlers="new Map([
        ['loaded', () => console.log('Report loaded')],
        ['rendered', () => console.log('Report rendered')],
        ['error', (event: any) => console.log(event.detail)]
    ])">
    </PowerBIReportEmbed>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { PowerBIReportEmbed } from 'powerbi-client-vue-js';

export default defineComponent({
  name: 'HomeView',
  components: {
    PowerBIReportEmbed,
  },
  data(){
    return{
      token: process.env.VUE_APP_AZURE_TOKEN, // COLOCAR O TOKEN NO ARQUIVO .ENV E REBUILDAR O PROJETO
      reportId: '7139a68c-a512-4989-9341-8063d0df8ae4',
      embedUrl: 'https://app.powerbi.com/reportEmbed?reportId=7139a68c-a512-4989-9341-8063d0df8ae4&groupId=285087f2-0e04-4366-9721-3a6658c7e153&w=2&config=eyJjbHVzdGVyVXJsIjoiaHR0cHM6Ly9XQUJJLUJSQVpJTC1TT1VUSC1CLVBSSU1BUlktcmVkaXJlY3QuYW5hbHlzaXMud2luZG93cy5uZXQiLCJlbWJlZEZlYXR1cmVzIjp7Im1vZGVybkVtYmVkIjp0cnVlLCJ1c2FnZU1ldHJpY3NWTmV4dCI6dHJ1ZX19'
    }
  }
});
</script>
<style lang="scss" scoped>
.powerbi{
  height: 90% ;
  width: 90% ;
  
}
</style>
