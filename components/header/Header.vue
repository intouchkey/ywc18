<template>
  <div>
    <FirstNavBar :provinces="provinces"></FirstNavBar>
    <SecondNavBar></SecondNavBar>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: ['provinces'],
}
</script>

<style></style>
