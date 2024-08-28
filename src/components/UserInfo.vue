<template>
  <section>
    <base-card>
      <template v-slot:header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </base-card>
  </section>
</template>

<script>
import BaseBadge from "./BaseBadge.vue";
import BaseCard from "./BaseCard.vue";

export default {
  components: {
    BaseBadge,
    BaseCard,
  },
  props: ["fullName", "infoText", "role"],
};
</script>
