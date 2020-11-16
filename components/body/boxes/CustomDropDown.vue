<template>
  <div class="custom-drop-down-container">
    <p class="topic">{{ topic }}</p>
    <b-dropdown
      block
      size="sm"
      split
      :text="defaultText"
      class="custom-dropdown"
      variant="outline-secondary"
      split-variant="outline-secondary"
      menu-class="w-100"
    >
      <b-dropdown-item v-for="item in items" :key="item" :name="item">{{
        item
      }}</b-dropdown-item>
    </b-dropdown>
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
  padding-bottom: 15px;
}
.topic {
  font-weight: bolder;
}
</style>
