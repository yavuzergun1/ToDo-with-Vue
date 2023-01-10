<script>
export default {
  inject: ['messageToChild']
}
</script>

<template>
  <p>
    Message to grand child: {{ messageToChild }}
  </p>
</template>