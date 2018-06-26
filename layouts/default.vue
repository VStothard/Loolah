<template>
  <div>
    <TheNavigation />
    <main>
      <nuxt/>
    </main>
    <TheFooter />
  </div>
</template>

<script>
  import TheNavigation from '@/components/TheNavigation/TheNavigation'
  import TheFooter from '@/components/TheFooter/TheFooter'

  export default {
    components: {
      TheNavigation,
      TheFooter
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
