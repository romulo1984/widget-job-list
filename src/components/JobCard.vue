<template>
    <div class="card">
        <div class="header-card">
            <h3>{{job.name}}</h3>
        </div>
        <div class="sub-header-card" v-if="config.show_company || config.show_industry">
            <div class="media">
                <div class="media-body media-middle">
                    <div v-if="config.show_company">
                        <span v-if="job.confidential" class="text-muted">
                        <i>Empresa confidencial</i><br>
                        </span>
                        <h5 v-if="!job.confidential">{{job.company}}</h5>
                    </div>
                    <span v-if="config.show_industry">{{job.industry}}</span>
                </div>
            </div>
        </div>
        <div class="inner-card" v-if="config.show_location">
            <span class="fa fa-fw fa-map-marker text-muted"></span> {{job.location}}
        </div>
        <div class="inner-card" v-if="config.show_salary">
            <span class="fa fa-fw fa-usd text-muted"></span> {{job.salary}}
        </div>
    </div>
</template>

<script>
export default {
  name: 'JobCard',
  props: {
    config: {
      type: Object
    },
    job: {
      type: Object
    }
  }
}
</script>

<style scoped lang="less">
    @import "../assets/less/profissa/_variables.less";

    .card {
        position:relative;
        background-color: @branco;
        margin-bottom: @gutter/2;
        margin-top: @gutter/2;
        padding: @gutter/2;
        .border-rounded(5px);
    }
    .header-card {
        color:@preto;
        h3 {
            margin:10px 0 @gutter/2;
        }
    }
    .footer-card {
        margin: 0 -@gutter/2;
        padding: @gutter/2 @gutter/2 0;
    }
    .sub-header-card {
        color:@preto;
        margin: 0 -@gutter/2;
        padding:@gutter/3 @gutter/2;
        border-top:1px solid darken(@creme, 8%);
        h5 {
            font-weight: 600;
            margin:0 0 @gutter/4;
        }
    }
    .inner-card {
        margin: 0 -@gutter/2;
        padding:@gutter/3 @gutter/2;
        border-top: 1px solid darken(@creme, 8%);
    }
</style>