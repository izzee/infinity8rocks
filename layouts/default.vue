<template>
  <div :class="`${this.$route.name} default-layout`">
    <Nav/>
    <main>
      <PageTitle/>
      <CustomCursor/>
      <Nuxt/>
    </main>
  </div>
</template>
