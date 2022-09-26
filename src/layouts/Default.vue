<template>
  <div>
    <slot />
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<style>
body,
html {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue',
    Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
  background: #141844;
  background: linear-gradient(
    190deg,
    rgba(20, 24, 68, 1) 0%,
    rgba(48, 33, 81, 1) 36%,
    rgba(148, 72, 118, 1) 61%,
    rgba(218, 112, 134, 1) 100%
  );
}

.layout,
main,
.container {
  height: 100%;
}
p {
  color: white;
  font-size: 1.125rem;
}
h1,
h2,
h3,
.title {
  color: #ef8089;
  font-weight: bold;
}
a {
  color: #367ba1;
}
</style>
