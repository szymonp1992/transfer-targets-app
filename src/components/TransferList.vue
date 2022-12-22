<template>
  <section>
    <TabSwitcher
      @open-targets-tab="openTargets"
      @open-add-target-tab="openAddTarget"
    ></TabSwitcher>
    <div v-if="targetsTabOpen">
      <Target
        v-for="target in targets"
        :key="target.id"
        :name="target.name"
        :club="target.currentClub"
        :price="target.price"
        :profile="target.profile"
        @remove-target="deleteTarget(target.id)"
      ></Target>
    </div>
    <keep-alive
      ><NewTargetTab
        v-if="!targetsTabOpen"
        @save-new-target="fetchNewTarget"
      ></NewTargetTab
    ></keep-alive>
  </section>
</template>

<script>
import TabSwitcher from './TabSwitcher.vue';
import NewTargetTab from './NewTargetTab.vue';
import Target from './Target.vue';

export default {
  components: {
    TabSwitcher,
    NewTargetTab,
    Target,
  },
  data() {
    return {
      targetsTabOpen: true,
      targets: [
        {
          id: '0001',
          name: 'Djed Spence',
          currentClub: 'Middlesbrough',
          price: '20',
          profile:
            'https://www.transfermarkt.pl/djed-spence/profil/spieler/483348',
        },

        {
          id: '0002',
          name: 'Christian Eriksen',
          currentClub: 'Brentford FC',
          price: '0',
          profile:
            'https://www.transfermarkt.pl/christian-eriksen/profil/spieler/69633',
        },
      ],
    };
  },
  methods: {
    openTargets() {
      this.targetsTabOpen = true;
    },
    openAddTarget() {
      this.targetsTabOpen = false;
    },
    fetchNewTarget(name, club, value, link) {
      const newTarget = {};
      newTarget.id = Date.now();
      newTarget.name = name;
      newTarget.currentClub = club;
      newTarget.price = value;
      newTarget.profile = link;
      this.targets.push(newTarget);
    },
    deleteTarget(identifier) {
      const index = this.targets.findIndex((arr) => arr.id === identifier);
      this.targets.splice(index, 1);
    },
  },
};
</script>

<style scoped>
section {
  margin: 20px;
}
</style>