<template>
  <h1>Nav</h1>
</template>

<style>
h1 {
  z-index: 100000000;
}
#nav {
  justify-content: center;
  flex-shrink: 0;
}

a {
  display: flex;
  width: 10.5rem;
  text-decoration: none;
  color: var(--text-color);
}

.logo {
  width: 10rem;
  position: absolute;
  left: 6.5%;
  top: 19.5%;
}

.icon {
  padding-right: 0.6rem;
  padding-bottom: 0.5rem;
}
#contact {
  padding-bottom: 0.1rem;
}
#donate {
  padding-bottom: 0.1rem;
}
.group {
  display: flex;
  width: 12rem;
  align-self: center;
}

a:visited {
  color: var(--text-color);
}
@media screen and (max-width: 1400px) {
  .group {
    width: 10rem;
  }
}

@media screen and (max-width: 1200px) {
  .logo {
    width: 7rem;
  }
  .icon {
    width: 1.5rem;
  }
  .group {
    font-size: 1.2rem;
    width: 9rem;
  }
}

@media screen and (max-width: 992px) {
}

@media screen and (max-width: 768px) {
  .logo {
    width: 6rem;
  }
}
@media screen and (max-width: 576px) {
  #logo {
    width: 1rem;
  }
}
</style>
