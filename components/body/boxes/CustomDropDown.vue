<template>
  <div class="custom-drop-down-container">
    <p class="topic">{{ topic }}</p>
    <select :text="defaultText">
      <option class="first-op" value="" disabled selected>
        {{ defaultText }}
      </option>
      <option v-for="item in items" :key="item" :name="item">{{ item }}</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'CustomDropDown',
  props: ['items', 'topic', 'defaultText'],
}
</script>

<style>
.custom-drop-down-container {
  margin-bottom: 20px;
}
select {
  width: 100%;
  padding: 5px;
  border-color: #ececec;
}
.topic {
  font-weight: bolder;
}
.first-op {
  color: #ececec;
}
</style>
