<template>
  <div>
    <virtual-list :list="list" :options="options" :height="height">
      <template #default="props">
        <!-- you can get current item of list at here -->
        Row: {{ props.data }}
      </template>
    </virtual-list>
  </div>
</template>
<script setup lang="ts">
import { UseVirtualList as virtualList } from './component'

const options = {
  itemHeight: 22,
}
const height = '600px'
const list = Array.from(Array(99999).keys())
</script>
