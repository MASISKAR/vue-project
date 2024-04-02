<script>
import ExchangeNew from './components/ExchangeNew.vue';
import Welcome from './components/Welcome.vue';

export default {
  components: {
    ExchangeNew,
    Welcome
  },
};
</script>

<template>
<main>
<ExchangeNew />
<Welcome name="John" :age="34" surname="Smith"/>
<Welcome name="Alex" :age="24"/>
<Welcome name="Sarah"/>

</main>
</template>


