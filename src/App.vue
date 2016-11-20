<template>
  <div class="bg-creme" :style="style">
    <img src="./assets/img/logo-profissa.png" alt="Profissa" width="140">
    <hr style="border-bottom:1px solid #ccc">
    <p style="margin-top:10px">
      Confira algumas vagas de emprego
    </p>
    <JobCard v-for="job in jobs" :job="job" :config="config"></JobCard>
  </div>
</template>

<script>
import JobCard from './components/JobCard'

export default {
  name: 'app',
  components: {
    JobCard
  },
  computed: {
    config () {
      return {
        show_location: (this.$route.query.show_location !== undefined) ? JSON.parse(this.$route.query.show_location) : true,
        show_salary: (this.$route.query.show_salary !== undefined) ? JSON.parse(this.$route.query.show_salary) : true,
        show_industry: (this.$route.query.show_industry !== undefined) ? JSON.parse(this.$route.query.show_industry) : true,
        show_company: (this.$route.query.show_company !== undefined) ? JSON.parse(this.$route.query.show_company) : true
      }
    },
    style () {
      return {
        width: (this.$route.query.width !== undefined) ? this.$route.query.width : '100%',
        minHeight: '300px',
        height: (this.$route.query.height !== undefined) ? this.$route.query.height : '',
        overflow: 'auto',
        padding: '15px'
      }
    }
  },
  data () {
    return {
      jobs: [
        {
          name: 'Purificador de Parafraseamento',
          company: 'HR Solutions',
          industry: 'Academia de Esportes / Artes Marciais',
          location: 'Jardim da Penha, Vitória-ES',
          salary: 'R$ 2.000,00 a R$ 2.200,00',
          confidential: false
        },
        {
          name: 'Coisador de Negoçamento',
          company: 'HR Solutions',
          industry: 'Academia de Esportes / Artes Marciais',
          location: 'Jardim da Penha, Vitória-ES',
          salary: 'R$ 3.000,00 a R$ 4.200,00',
          confidential: false
        }
      ]
    }
  }
}
</script>

<style src="assets/less/app.less" lang="less"></style>
