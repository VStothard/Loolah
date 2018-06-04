<template>
  <div>
    <TheNavigation />
    <main>
      <nuxt/>
    </main>
  </div>
</template>

<script>
  import TheNavigation from '@/components/TheNavigation/TheNavigation'

  export default {
    components: {
      TheNavigation,
    }
  }
</script>
<style>
html
{
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;

}
*, *:before, *:after
{
  box-sizing: border-box;
  margin: 0;
}
</style>
