<template>
  <div>
    <NuxtRouteAnnouncer />
    <NuxtWelcome />
  </div>
</template>

<script setup>
const email = ref('maeldev3@gmail.com');
const password = ref('password');


const login = async () => {
  const { data, error } = await useFetch('https://api.staging.voomgle.com/api/login', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'Accept': 'application/json'
      },
      body: {
        email: email.value,
        password: password.value
      }
    });

    console.log(data.value);
};

login();
</script>