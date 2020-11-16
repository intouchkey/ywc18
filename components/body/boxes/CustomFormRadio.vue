<template>
  <div>
    <p class="topic">{{ topic }}</p>
    <b-form-group>
      <b-form-radio
        v-for="item in items"
        v-model="localSelected"
        :key="item"
        :name="item"
        :value="item"
      >
        {{ item }}
      </b-form-radio>
    </b-form-group>
  </div>
</template>

<script>
export default {
  name: 'CustomFormRadio',
  props: ['items', 'topic', 'selected'],
  computed: {
    localSelected: {
      get: function () {
        return this.selected
      },
      set: function (newValue) {
        this.$emit("update-selected", newValue);
      },
    },
  },
}
</script>

<style>
.topic {
  font-weight: bolder;
}
</style>
