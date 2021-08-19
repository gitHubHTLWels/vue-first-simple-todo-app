<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <h3>This is your XXX-ToDo !!</h3>
  </div>

  <div>
    <input placeholder="Add a ToDo" type="text" />
  </div>
  <ul>
    <li>
      <span>One </span>
      <button>X</button>
    </li>
    <li>
      <span>Two </span>
      <button>X</button>
    </li>
    <li>
      <span>Three </span>
      <button>X</button>
    </li>
  </ul>
</template>

<script>
// @ is an alias to /src
// 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
</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
  width: 200px;
  margin: 20px auto 0;
}
li {
  border: 1px solid;
  display: flex;
  margin-buttom: 10ox;
}
li span {
  flex-grow: 1;
}
</style>
