<template>
  <div>
    <h1>Hallo</h1>
    <p>{{text}}</p>
    <h2>Data from Backend:</h2>
    <p v-if="backendData?.msg">{{backendData.msg}}</p>
    <p v-else>No data available</p>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
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
