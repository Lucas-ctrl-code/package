<template>
  <component
    :is="as"
    v-bind="buttonProps"
    :class="computedClass"
    :href="href"
    :type="as === 'button' ? type : undefined"
    :disabled="disabled"
    @click="onClick"
  >
    <slot />
  </component>
</template>

<script setup lang="ts">
import { computed, defineProps, defineEmits } from 'vue'

const props = defineProps({
  as: { type: String, default: 'button' },
  href: { type: String, default: '' },
  type: { type: String, default: 'button' },
  disabled: { type: Boolean, default: false },
  class: { type: [String, Array, Object], default: '' },
})
const emit = defineEmits(['click'])

const computedClass = computed(() => props.class)

const buttonProps = computed(() => {
  const { as, href, type, class: _class, ...rest } = props
  return rest
})

function onClick(e: Event) {
  if (props.disabled) {
    e.preventDefault()
    return
  }
  emit('click', e)
}
</script>
