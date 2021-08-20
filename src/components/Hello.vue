<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      This is our toolbox to tests connections, sevice mesh and others boring stuff
    </p>
    <h3>Kubernetes</h3>
    <ul>
      <li><a href="http://localhost:8080/#/Featureflag" target="_blank" rel="http://localhost:8080/#/Featureflag">Feature Flag</a></li>
      <li><a href="http://localhost:8080/#/Fetch secret" target="_blank" rel="http://localhost:8080/#/Featureflag">Fetching Secrets</a></li>
    </ul>
    <h3>Essential Links/Docs</h3>
    <ul>
      <li><a href="https://helm.sh/docs/" target="_blank" rel="noopener">Helm</a></li>
      <li><a href="https://kubernetes.io/docs/home/" target="_blank" rel="noopener">Kubernetes</a></li>
      <li><a href="https://docs.docker.com/" target="_blank" rel="noopener">Docker</a></li>
      <li><a href="https://buildah.io/" target="_blank" rel="noopener">Buildah</a></li>
      <li><a href="https://www.terraform.io/docs/index.html" target="_blank" rel="noopener">Terraform</a></li>
      <li><a href="https://github.com/hashicorp/terraform-cdk" target="_blank" rel="noopener">TF CDK</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
