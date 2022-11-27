<template>
  <div>
    <h1>Hallo</h1>
    <p>{{text}}</p>
    <p>{{backendData.msg}}</p>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  mounted() {
    console.log("Mik")
    },
  async asyncData() {
    const url = 'http://host.docker.internal:8080/'
    let text;
    let backendData;
    await fetch(url).then(res => res.json()).then((data) => {
      backendData = data;
      console.log(data)
    }).catch(er => console.error(er))

   await fetch('https://jsonplaceholder.typicode.com/todos/1')
      .then(response => response.json())
      .then((json) => {
        console.log(json)
        text = json.title
      })
    return { text,backendData }
  }
}

</script>
