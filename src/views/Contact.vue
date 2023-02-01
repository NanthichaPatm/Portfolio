<script>
import feather from "feather-icons";
import ContactDetails from "@/components/contact/ContactDetails.vue";

export default {
  components: {
    ContactDetails,
  },
  data: () => {
    return {
      contacts: [
        {
          id: 1,
          name: "220/64 Bond St, Bangphut,Pak Kret District 11120 Nonthaburi",
          icon: "map-pin",
        },
        {
          id: 2,
          name: "nanthicha.patm@gmail.com",
          icon: "mail",
        },
        {
          id: 3,
          name: "+66974914245",
          icon: "phone",
        },
      ],
    };
  },
  mounted() {
    feather.replace();
  },
  updated() {
    feather.replace();
  },
  methods: {},
};
</script>

<template>
  <div
    class="
      container
      mx-auto
      flex flex-col-reverse
      md:flex-row
      py-5
      md:py-10 md:mt-10
    "
  >
    <!-- Contact details -->
    <ContactDetails :contacts="contacts" />
  </div>
</template>
