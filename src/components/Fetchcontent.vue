<template>
  <div>
    <h3 id="flaglist" class="ui huge header" style="text-align: center;">Flags Testing</h3>
    <div class="container container-custom">
      <div class="leftbox">
          <h2 class="ui header">List of flags</h2>
          <div class="item" v-for="flags in flagslist" v-bind:key="flags">
            <i class="large tag alternate middle aligned icon"></i>
            <button @click="getFlagData(flags.name)" class="flagitem">{{flags.key }} - {{flags.name }}</button>
          </div>
      </div>

      <div class="rightbox">
        <div>
          <h2 class="ui header" id="rbox-header">Content return</h2>
        </div>
        <div v-html="flagDetail"></div>
      </div>
    </div>
  </div>


    <!-- <ul id="flagul">
      <li v-for="flags in flagslist" v-bind:key="flags"></li>
    </ul> -->

</template>


<script>
import axios from 'axios';
export default {
  name: 'Fetchcontent',
  props: {
    msg: String
  },
  data(){
      return {
          flagslist: [],
          flagData: null
      }
  },
  mounted() {
    fetch('http://localhost:8082/api/v1/flags')
          .then(res => res.json())
          .then(data => this.flagslist = data.flags.[0].variants)
          .catch(err => console.log(err.message))
  },
  computed: {
      flagDetail: function() {
        return this.flagData;
      }
    },
  methods: {
      getFlagData(id) {
        axios({
          method: "get",
          url: `http://demoks.aks.op-svc.com/creds`,
          headers: {
            'x-my-header': `${id}`
          }
        })
          .then(result => {
            this.flagData = result.data;
          })
      }
    },

}
</script>


<style>
.container-custom {
  display: flex; /* or inline-flex */
  flex-direction: row;
  /* background-color: #2c3e50; */
  border-top: 2px solid rgba(34,36,38,.15);
  border-bottom: 2px solid rgba(34,36,38,.15);
  height: 800px;
}

.flagitem {
  color: #2c3e50;
  font-size: 14px;
  margin-bottom: 10px;
  width:88%;
  text-align: left;
  padding-left: 2%;
  border: none;
  border-bottom: 2px solid rgba(34,36,38,.15);
}

.flagitem:hover {
  color: white;
  background-color: rgba(34,36,38,.15);
  font-size: 14px;
  margin-bottom: 10px;
  width:88%;
  text-align: left;
  padding-left: 2%;
  border: none;
  border-bottom: 2px solid rgba(34,36,38,.15);
}

.leftbox {
  width: 20%;
  border-bottom: 10px;
  border-color: dimgray;
  padding: 45px 0px 0px 65px;
  text-align: left;
}

.rightbox {
  text-align: center;
  width: 80%;
  padding: 45px 65px 0px 0px;
  border-left: 2px solid rgba(34,36,38,.15);
}

#rbox-header {
  text-align: center;
  margin-bottom: 50px;
}

</style>
