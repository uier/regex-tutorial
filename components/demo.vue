<script>
import { ref, computed } from 'vue'
import HighlightableInput from './HighlightableInput.vue'

export default {
  props: {
    defaultPattern: String,
    defaultFlags: String,
    defaultText: String,
  },
  setup(props) {
    const pattern = ref(props.defaultPattern)
    const flags = ref(props.defaultFlags)

    const regex = computed(() => (pattern.value ? new RegExp(pattern.value, flags.value) : ''))

    return {
      pattern,
      flags,
      regex,
      defaultText: props.defaultText,
    }
  },
}
</script>

<template>
  <div class="mt-16 flex flex-col font-mono">
    <div class="flex mb-16">
      <div :class="['relative h-10', !pattern && 'empty']">
        <input
          id="pattern"
          v-model="pattern"
          class="
            mr-[25px]
            shadow
            appearance-none
            border
            rounded
            w-[350px]
            py-2
            px-3
            text-2xl text-teal-600
            leading-tight
            outline-none
            focus:shadow-none focus:border-teal-500
            transition-all
          "
          type="text"
        />
        <label for="pattern" class="absolute left-2 transition-all bg-white px-1"> Pattern </label>
      </div>
      <div :class="['relative h-10', !flags && 'empty']">
        <input
          id="flags"
          v-model="flags"
          class="
            shadow
            appearance-none
            border
            rounded
            w-[125px]
            py-2
            px-3
            text-2xl text-teal-600
            leading-tight
            outline-none
            focus:shadow-none focus:border-teal-500
            transition-all
          "
          type="text"
        />
        <label for="flags" class="absolute left-2 transition-all bg-white px-1"> Flags </label>
      </div>
    </div>

    <HighlightableInput
      highlight-style="background-color: lightpink"
      :highlight="[
        {
          text: regex,
        },
      ]"
      :value="defaultText"
    />
  </div>
</template>

<style>
label {
  top: 0%;
  transform: translateY(-50%);
}
.empty input:not(:focus) + label {
  top: 60%;
  transform: translateY(-50%);
  font-size: 1.5rem;
  line-height: 2rem;
}
</style>
