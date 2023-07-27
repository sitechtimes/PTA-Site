<template>
  <div>
    <Navbar />
    <slot />
    <ScrollTop />
  </div>
</template>

<style>
/* width */
::-webkit-scrollbar {
  width: 15px;
}
::-webkit-scrollbar-track {
  background: linear-gradient(
    180deg,
    #ffc498 0%,
    #fce5ac 20%,
    #f8e4b2 30%,
    #fbefd7 75%,
    #fff 85%
  );
}
/* Handle */
::-webkit-scrollbar-thumb {
  background: #483221;
  border-radius: 15px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #543b28;
}
</style>
