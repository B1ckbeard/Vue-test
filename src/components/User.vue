<template>
    <div className="user">
        <p>{{ user.name }}</p>
        <p>{{ user.email }} - ({{ user.pass }})</p>
    </div>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
      required: true
    }
  }
}
</script>

<style>
.user {
    width: 300px;
    height: 80px;
    border: 1px solid black;
    background-color: aliceblue;
    border-radius: 4px;
    margin-bottom: 10px;
    padding: 10px;
}
</style>