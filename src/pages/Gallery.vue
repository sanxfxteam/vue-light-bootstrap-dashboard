<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-xl-4" v-for="capacity in capacities" v-bind:key="capacity">
          <stats-card>
            <div slot="header" class="icon-warning">
              <i class="nc-icon nc-chart text-warning"></i>
            </div>
            <div slot="content">
              <p class="card-category">Capacity</p>
              <h4 class="card-title">{{ capacity }}</h4>
            </div>
            <div slot="footer">
              <div><i class="fa fa-refresh"></i>Updated now</div>
              <div><button class="btn btn-primary" v-if="capacity != '2GB'" @click.prevent="refresh">Refresh</button></div>
            </div>
          </stats-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  import StatsCard from 'src/components/Cards/StatsCard.vue'

  export default {
    components: {
      StatsCard
    },
    data () {
      return {
        capacities: ['1GB', '2GB', '4GB', '1GB', '2GB', '4GB', '1GB', '2GB', '4GB', '1GB', '2GB', '4GB'],
      }
    },
    methods: {
      refresh() {
        alert('refreshing')
      }
    }
  }
</script>
<style>

</style>
