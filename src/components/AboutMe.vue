<template>
  <section id="about" class="hide-overflow">
    <v-layout white>
      <v-flex xs12 md6 pa-5 class="mb-5 px-5">
        <base-bubble-1 style="transform: translate(5%, -5%)"/>
        <base-Subheading class="primary--text">Additional Informations</base-Subheading>
        <v-layout v-for="(info, i) in infos" :key="i+'infos'">
          <base-text class="mb-4">
            <v-icon color="secondary">{{info.icon}}</v-icon>
            {{info.details}}
          </base-text>
        </v-layout>
       <v-layout v-for="(skill, i) in skills" :key="i+'b'" style="color: black;" wrap>
          <v-flex xs6 text-uppercase v-text="skill.name"/>
          <v-flex xs6 text-xs-right v-text="`${skill.value}%`"/>
          <v-tooltip top>
            <template v-slot:activator="{ on }">
              <v-progress-linear :value="skill.value" v-on="on" color="secondary" height="8"/>
            </template>
            <span>{{skill.value}}%</span>
          </v-tooltip>
        </v-layout>
        <v-divider class="mr-10" width="70%"></v-divider>
        <base-Subheading class="primary--text mt-5">Contact Information</base-Subheading>
        <v-layout v-for="(info, i) in items" :key="i+'*'">
          <base-text class="mb-4">
            <v-icon color="secondary">{{info.icon}}</v-icon>
            {{info.account}}
          </base-text>
        </v-layout>
        <!-- <base-heading class="mt-3 primary--text">Quotes</base-heading>
        <base-text class="mb-1">"If there is no way , then create your own way."</base-text>
      </v-flex>
      <v-flex hidden-sm-and-down md6>
        <v-img
          :lazy-src="require('@/assets/logo.png')"
          :src="require('@/assets/aboutme.png')"
          height="100%"
        />
      </v-flex>
    </v-layout>
  </section>
</template>
<script>
export default {
  data: () => ({
    skills: [
      {
        name: "Backend Development",
        value: 100
      },
      {
        name: "Frontend Development",
        value: 75
      },
      {
        name: "Database Management",
        value: 90
      }
    ],
    infos: [
      {
        icon: "mdi-school",
        details: "University of San Carlos Talamban Campus",
        title: "School"
      },
      {
        icon: "mdi-map-marker",
        details: "Nasipit Road, Talamban, Cebu City, Cebu Ph",
        title: "Address"
      },
      {
        icon: "mdi-briefcase",
        details: "Intern/Developer at CloudNinjaPh",
        title: "Experience"
      }
    ],
    items: [
      { account: "yoltorres24@gmail.com", icon: "mdi-gmail" },
      { account: "www.facebook.com/yoltorres24", icon: "mdi-facebook" },
      { account: "www.github.com/quinyolxd99", icon: "mdi-github-circle" },
      {
        account: "www.linkedin.com/in/leonilojr-torres-722027196",
        icon: "mdi-linkedin-box"
      },
      {
        account: "09266725841/09973312100",
        icon: "mdi-phone"
      }
    ]
  })
};
</script>
